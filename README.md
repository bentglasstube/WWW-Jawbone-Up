# NAME

WWW::Jawbone::Up - Unofficial Jawbone UP API

# SYNOPSIS

    use WWW::Jawbone::Up;

    my $up = WWW::Jawbone::Up->connect('alan@eatabrick.org', 's3kr3t');

    my $user = $up->user;
    my $score = $up->score;

    say $user->name . ' walked ' . $score->move->distance . 'km today';

    my $hours = int($score->sleep->asleep / 3600);
    my $minutes = int($score->sleep->asleep / 60); % 60;

    say $user->name . " slept for ${hours}h${minutes}m last night";

# DESCRIPTION

WWW::Jawbone::Up is a perl binding to the unofficial Jawbone UP API.  After
authenticating you can find interesting bits of data.  The version number of
this library should reflect the associated version of the Jawbone API but I
have no way of knowing if they will be sane with their version numbers so we'll
see how that pans out.

# METHODS

## connect($email, $password)

Authenticates with the API.  Will return undef if there are any errors,
possibly also dying or warning about them.

## user()

Returns a [WWW::Jawbone::Up::User](http://search.cpan.org/perldoc?WWW::Jawbone::Up::User) object representing the currently
authenticated user.

## feed($date)

Returns an array of [WWW::Jawbone::Up::Feed](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Feed) objects for the given `$date`.
If no date is given, the current date is used.

## score($date)

Returns a [WWW::Jawbone::Up::Score](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Score) object for the given `$date`.  If no date
is given, the current date is used.

## band($start, $end)

Returns an array of [WWW::Jawbone::Up::Tick](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Tick) objects for the given time range.
Both `$start` and `$end` should be epoch times (seconds since epoch).  If no
range is given, I think the current day is used, but I haven't really
researched that fact too much.

## workouts($date)

Returns an array of [WWW::Jawbone::Up::Workout](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Workout) objects for the give `$date`.
If no $date is given, I think some number of recent workouts are given, but I
haven't really researched that fact too much.

# TODO

The documentation for this distribution is utterly lacking.  I will fix that
sometime soon.

# AUTHOR

Alan Berndt <alan@eatabrick.org>

# COPYRIGHT

Copyright 2013- Alan Berndt

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO

[WWW::Jawbone::Up::Feed](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Feed)
[WWW::Jawbone::Up::Score](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Score)
[WWW::Jawbone::Up::Tick](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Tick)
[WWW::Jawbone::Up::User](http://search.cpan.org/perldoc?WWW::Jawbone::Up::User)
[WWW::Jawbone::Up::Workout](http://search.cpan.org/perldoc?WWW::Jawbone::Up::Workout)
