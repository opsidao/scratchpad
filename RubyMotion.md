# Errors not too descriptive

Imagine you have this code in your AppDelegate:

```Ruby
class AppDelegate
  def application(application, didFinishLaunchingWithOptions:launchOptions)
    UIAlertView.alloc.initWithTitle("Heeey!",
      message: "This is a message man!",
      delegate: nil,
      cancelButtonTitle: "Ok",
      otherButtontitles: nil).show

    true
  end
end
```

If you tried to run that you would get this error:

```
2013-11-25 13:14:31.556 ArchiSnapper[52037:80b] app_delegate.rb:7:in `application:didFinishLaunchingWithOptions:': undefined method `initWithTitle' for #<UIAlertView:0x8cd2240> (NoMethodError)
2013-11-25 13:14:31.559 ArchiSnapper[52037:80b] *** Terminating app due to uncaught exception 'NoMethodError', reason: 'app_delegate.rb:7:in `application:didFinishLaunchingWithOptions:': undefined method `initWithTitle' for #<UIAlertView:0x8cd2240> (NoMethodError)
```

Reding this error, can you guess what's wrong with our original code?

The problem is that we wrote **otherButtontitles:** instead of
**otherButtonTitles:**, but you wouldn't know it from the error.
