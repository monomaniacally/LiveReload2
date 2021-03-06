LiveReload 2
============

LiveReload is an essential tool for web developers, and is currently the top paid developer tool on the Mac App Store in many countries.

Please remember that this is not under a traditional free software license, but under a specific set of moral terms. I'm happy with you forking the source code, sharing your modifications and sharing binaries with your friends, but please don't post the binaries publicly without my permission, and don't fork the project under a different name. I want every user to buy a license by default, though, unless you have a good reason not to pay (in which case just ask me for a free license or copy a binary from someone else, there is no copy protection).

See http://livereload.com for licensing info and an optional backstory on that.

If you'd like to reuse some of the classes, please contact me and I'm likely to publish those under MIT.


AppNewsKit
==========

(See Stats.h/m. This is a seriously cool shit to communicate with your live users. consider those files to be under MIT; I will extract and document it properly soon.)

* Collect usage statistics
* Deliver news to your users

Example ping.txt:

    {
        "see_explanation_at": "http://help.livereload.com/kb/about-us/usage-statistics-privacy-policy",
        "messages": [
            {
                "title": "MyApp on the Mac App Store!",
                "message": "MyApp 2.1 has been released on the Mac App Store, and is on sale (50% off)! Do you want to learn more about it?",
                "id": "myapp-2.0.0-release",
                "version": [">=2.0 <3.0"],
                "status": ["unregistered"],
                "stats": {
                    "stat.reloads": { "min": 10 }
                },
                "delay_if_nagged_within": "3d",
                "remind_later_in": "5d",
                "deliver_after": "2011-12-08 16:33:00",
                "wait_until_good_time": true,
                "delivery_on_stats": {
                    "or": {
                        "stat.reloads.last": { "within": 30 },
                        "stat.launch.first": { "within": 120 }
                    }
                },
                "random_percentage": 50,
                "primary_button_url": "http://myapp.com/mas/",
                "primary_button_title": "Visit Mac App Store"
            }
        ]
    }
