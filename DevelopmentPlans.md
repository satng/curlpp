# Development Plans #

So, what's next? I have some ideas for future releases. If you want to suggest some feature, don't be shy and send me an email (see at the bottom of the page).

## Version 0.6.0 (Out) ##

**Exception safe feature**. What's exactly the matter? Isn't supposed to be already exception safe? Well, the problem is when you work with C++ callbacks that are called within C code. What will happen if the callback throw an exception? The exception will go through the C code. This will completely break the C code. So, you need to be sure that it's impossible that an exception is thrown, without being handled in your callback. So, I want to add some code that will handle any exception thrown and rethrow it in the C++ code, meaning in the cURLpp::Easy::perform function. Then, you'll be able to throw exceptions, without being scared to break libcURL's execution.

**Functors**. At this time we use plain functions as callbacks. However, if you want to use a member function, you need to create a function that will cast your data (that you previously set on the handle), and then call your member function. I want to use functors instead. If you don't know what are functors, check this: http://www.tutok.sk/fastgl/callback.html.

## Version 0.7.0 (Out) ##

**Multi interface**. We need to add the Multi interface. Here's the description from libcURL's documentation:
??The multi interface is the asynchronous brother in the family and it also offers multiple transfers using a single thread and more. The multi interface introduces several new abilities that the easy interface refuses to offer. They are mainly:
  * Enable a "pull" interface. The application that uses libcurl decides where and when to ask libcurl to get/send data.
  * Enable multiple simultaneous transfers in the same thread without making it complicated for the application.
  * Enable the application to select() on its own file descriptors and curl's file descriptors simultaneous easily.

## Version 0.8.0 ##

**Share interface**. Right now, we don't provide any wrapping for the Share interface. Mostly, this wrapping will depend on the functor feature. This is the description from the libcURL documentation: The share interface was added to enable sharing of data between curl "handles". You can have multiple easy handles share data between them. Have them update and use the same cookie database or DNS cache! This way, each single transfer will take advantage from data updates made by the other transfer(s).