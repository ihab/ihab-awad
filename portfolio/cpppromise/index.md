---
layout: page
title: CppPromise
---

CppPromise is a concurrent computing library I built at Verily with Limu Xiao, as part of the [Verily Retinal Camera](../verily_retinal_camera/) project.

## Introduction

> [!NOTE]
> We just got approval from Verily to Open Source CppPromise. Check it out at:
> [`github.com/cpppromise/cpppromise`](https://github.com/cpppromise/cpppromise)

The library allows programmers to build their C++ programs as a series of independent event loops, each with its own independent state, passing messages consisting of (logically) immutable data. A programmer can write an API for an event loop that manages a camera sensor in a system, for example, as follows:

{% highlight cpp %}
class CameraSensorProcess : public cpppromise::Process {
 public:
  cpppromise::Promise<Image> GetNextImageFromCamera();
}
{% endhighlight %}

Another event loop could then use this as:

{% highlight cpp %}
{
  myCameraProcess_->GetNextImageFromCamera().Then([](Image result) {
    // Do something with the result
    // This closure runs in the thread of the calling event loop
  });
}
{% endhighlight %}

Programmers can do idiomatic `Then()` chaining as they would in JavaScript, and avoid concurrent state modification hazards. A proper use of the system is one where application programmers do not use `std::thread` or `std::mutex` directly.

The system also includes a pub/sub mechanism that operates similarly.

This work allowed Verily people of all experience -- including mechanical engineers -- to contribute to the core C++ software without the usual hazards. This in turn allowed engineers with experience in machine learning, image processing, and the application domain, to work directly with us, and was both a morale and technical force multiplier.
