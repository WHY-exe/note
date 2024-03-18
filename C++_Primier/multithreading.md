# Passing Message Between Thread

C++ stl provides a way to establish one-way, use-once and 'single-producer-single-consumer' channel between thread. The api represent the two ends of the channel is std::promise(producer) and std::future(consumer) the example below show how to make useful of them:

```c++
#include <thread>
#include <future>
// you may want to include spdlog as your sub-project
#include "spdlog/spdlog.h"
int main()
{
	spdlog::info("hello world");
	std::promise<std::string> prms;
	std::future<std::string> futr = prms.get_future();
	auto thread1 = std::thread([](std::promise<std::string>&& prms){
		prms.set_value("1231456");
	}, std::move(prms));
	auto thread2 = std::thread([](std::future<std::string>&& futr){
		spdlog::info("msg from thread1: {}", futr.get());
	}, std::move(futr));
	thread1.join();
	thread2.join();
	return 0;
}
```

As it is shown up there, you achieve the message sharing in following steps:

1. bind the `std::future` to the `std::promise` you want to recieve message with
2. the `std::future::get()` would block the thread until the message is set in the `std::promise`

Note that it would be better to move the `std::promise` and std::future into the thread you would want to make use of them
