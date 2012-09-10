# ptail - Tail-f through http (python based)

The intended usecase of ptail is to get easy access to remote logfiles
over http without the need to install additional software on the server.

ptail is a simple tail that works over http (initially).
ptail uses an initial HEAD request to get the size of the file requested,
and then uses range requests to get only new content.
It's thus a complete client side solution.

The same method currently used with http can also be used with other protocols.


## Examples

    % ptail http://devserver1.foo.org/logs/auth.log
    Sep 10 04:09:01 localhost CRON[11620]: pam_unix(cron:session): session opened for user root by (uid=0)
    Sep 10 04:09:01 localhost CRON[11620]: pam_unix(cron:session): session closed for user root
    Sep 10 04:17:01 localhost CRON[12998]: pam_unix(cron:session): session opened for user root by (uid=0)
    Sep 10 04:17:01 localhost CRON[12998]: pam_unix(cron:session): session closed for user root
    Sep 10 04:39:01 localhost CRON[16696]: pam_unix(cron:session): session opened for user root by (uid=0)
    Sep 10 04:39:01 localhost CRON[16696]: pam_unix(cron:session): session closed for user root
    Sep 10 05:09:01 localhost CRON[22075]: pam_unix(cron:session): session opened for user root by (uid=0)
    Sep 10 05:09:01 localhost CRON[22075]: pam_unix(cron:session): session closed for user root
    Sep 10 05:17:01 localhost CRON[23571]: pam_unix(cron:session): session opened for user root by (uid=0)
    Sep 10 05:17:01 localhost CRON[23571]: pam_unix(cron:session): session closed for user root
    ...
