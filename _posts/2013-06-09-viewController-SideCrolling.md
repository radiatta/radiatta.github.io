---
layout: post
published: true
title: View Controller Side Scrolling on iOS.
---

<p align="justify"> I've created this quick example of a now common effect in iOS. The screen scrolling effect become popular on iOS 5 since it let us integrate extra menus into our viewControllers without the need of extra buttons or bars. <p> 

<p align ="center"><img src="/assets/HomeScroll.png" align="center" alt="Pokedex Home Scroll" height="600" width="340"></img></p>

<p align="justify">The main function used at this example are [animateWithDuration](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIView_Class/UIView/UIView.html#//apple_ref/occ/clm/UIView/animateWithDuration:animations:). Function that is activated on a button or gesture is recognized. </p>

<p align="justify">For this example we got [UISwipeGestureRecognizerDirectionLeft](https://developer.apple.com/library/ios/documentation/EventHandling/Conceptual/EventHandlingiPhoneOS/GestureRecognizer_basics/GestureRecognizer_basics.html) so once we detect the gesture we trigger our screen sidescrolling.</p>

  > Remember you have to place a viewcontroller over you mainViewController. If you fail to do this the delegate action of scrolling wont work since it will confuse where to move you desired view.

It's an immensely useful tool and improves our app designs.

{% highlight js %}
// Example of animateWithDuration

- (void) animateMainViewToLeft{
    //Animate mainView
    [UIView animateWithDuration:0.9 animations:^(void){
        _myMainView.frame = CGRectMake(0, 0, _myMainView.frame.size.width, _myMainView.frame.size.height);
    }];
    [_homeIcon setImage:[UIImage imageNamed:@"Pokeball.png"]];

}

- (void) animateMainViewToRight{
    //Animate mainView
    [UIView animateWithDuration:0.9 animations:^(void){
        _myMainView.frame = CGRectMake(280, 0, _myMainView.frame.size.width, _myMainView.frame.size.height);
    }];
    [_homeIcon setImage:[UIImage imageNamed:@"clickedPokeBall.png"]];
}

{% endhighlight %}

<p align="justify">Remember to create an if STATEMENT that triggers with your gesture recognizer or button press so we can check where the actual position of our view is. This way we can ensure where the code need to place our scrolled view.</p>


{% highlight js %} 
if(_myMainView.frame.origin.x > 0){
    [self animateMainViewToLeft];
    [_homeIcon setImage:[UIImage imageNamed:@"Pokeball.png"]];

}else{
    [self animateMainViewToRight];
    [_homeIcon setImage:[UIImage imageNamed:@"clickedPokeBall.png"]];
}
{% endhighlight %}

And declare you gesture recognizer on your viewDidLoad Method.

{% highlight js %}

UISwipeGestureRecognizer *leftSwipeGesture = [[UISwipeGestureRecognizer alloc]
    initWithTarget:self
    action: @selector
    navigationButtonPressed:)];

    
UISwipeGestureRecognizer *rightSwipeGesture = [[UISwipeGestureRecognizer alloc]
    initWithTarget:self
    action: @selector(navigationButtonPressed:)];
    
leftSwipeGesture.direction = UISwipeGestureRecognizerDirectionLeft;
    [self.view addGestureRecognizer:leftSwipeGesture];
    
rightSwipeGesture.direction = UISwipeGestureRecognizerDirectionRight;
    [self.view addGestureRecognizer:rightSwipeGesture];
{% endhighlight %}