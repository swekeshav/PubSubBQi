# PubSubBQi
__How to Run:__
1. Install [Visual Studio Community 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=16) from VisualStudio website
2. Download .NET desktop development workload
3. Open Visual Studio, select Clone or check out code 
4. Clone the Project from Github to a local repository
5. Open the solution file from src > TH.PubSub
6. Run the TH.PubSub.UI.Con application and test

__Create new publisher__
>var publisher = new Publisher();

__Create new subscriber__
>var subscriber = new Subscriber();

__Publish an object to a queue__
>publisher.Publish(object, queuename);

__Subscribe to a queue__
>subscriber.Subscribe(queuename);

__UnSubscribe from a queue__
>subscriber.UnSubscribe(queuename);


__Assumptions:__
* We need to address different queues by names (they are stored in MessageBroker QueuePool)
* QueuePool will have a default queue named "default"
* Default buffer limit for default queue is 5
* MessageBroker will be singleton (implemented manually, instead of using DI Framework)
* Subscribers cannot subscribe to same queue twice

__Xtensibility:__
* Write unit test cases
* Use ConcurrentDictionary for handling concurrency in multithreading scenarios
* Use async await for asynchronous handling of data while publishing and flushing notifications
* Use DependencyInjection to be able inject dependencies based on definition
* Use Typed Queues instead of named queues for better type-safety
* Instead of passing multiple parameters while PublishingToQueue, we can use a single dto object for 
* improved encapsulation and maintenance
* Allow users to delete queues except Default Queue
* Refactor for better naming and easier testing

