# Basmati - Battery Status Monitor

Set a charge limit to try to prolong the battery life of laptops without hardware charge limit. For example, recent Macbooks.

In short, it works by leaving the battery unaffected as much time as possible. Specifically:

 - It limits charging to 70%.
 - It starts charging below 30%.
 - If at boot the charge level is between 30% and 70%, it will inhibit charging. This means that if the Macbook is connected to a power outlet, it will not touch the battery at all (unless it doesn't receive enough power).

This might not work well for everybody, but it works well for me:

 - When I'm sitting at my desk, the Macbook is plugged in and because of the policy above the battery is not touched most of the time which should extend its lifetime.
 - Later at night I might watch a series and 30% battery life is more than enough for me (one episode uses around 5% of battery on MacOS).
 - Once it drops below 30%, it is recharged to 70% the next time I'm at my desk.

Does this save battery life? I hope so, and with what I know about lithium batteries I'm pretty sure it does. But I have no proof of this. If you're interested in learning more, I recommend reading [this page from AccuBattery](https://accubattery.zendesk.com/hc/en-us/articles/210224725-Charging-research-and-methodology) that goes into a lot more depth. The tl;dr is that what is most harmful to batteries is charging beyond 80% or so.

## Install

As root:

```
make install
systemctl start basmati
systemctl enable basmati
```

To check it's running:

```
systemctl status basmati
```

## License

BSD 3 clause.
