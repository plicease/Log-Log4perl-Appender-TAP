# Log::Log4perl::Appender::TAP [![Build Status](https://secure.travis-ci.org/plicease/Log-Log4perl-Appender-TAP.png)](http://travis-ci.org/plicease/Log-Log4perl-Appender-TAP)

Append to TAP output

# VERSION

version 0.02

# SYNOPSIS

    use Test::More tests => 1;
    use Log::Log4perl;
    

    LOG::Log4perl::init(\<<CONF);
    log4perl.rootLogger=ERROR, TAP
    log4perl.appender.TAP=Log::Log4perl::Appender::TAP
    log4perl.appender.TAP.method=diag
    log4perl.appender.TAP=layout=PatternLayout
    log4perl.appender.TAP=layout.ConversionPattern="[%rms] %m%n
    CONF
    

    DEBUG "this message doesn't see the light of day";
    ERROR "This gets logged to TAP using diag";
    

    pass 'okay';

# DESCRIPTION

This very simple appender sends log output to TAP using
[Test::Builder](http://search.cpan.org/perldoc?Test::Builder).  It only takes one special argument,
the method, which can be either `diag` or `note`.

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2013 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
