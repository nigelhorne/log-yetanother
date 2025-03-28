# NAME

Log::Abstraction - Logging abstraction layer

# VERSION

0.07

# SYNOPSIS

    use Log::Abstraction;

    my $logger = Log::Abstraction->new(logger => 'logfile.log');

    $logger->debug('This is a debug message');
    $logger->info('This is an info message');
    $logger->notice('This is a notice message');
    $logger->trace('This is a trace message');
    $logger->warn({ warning => 'This is a warning message' });

# DESCRIPTION

The `Log::Abstraction` class provides a flexible logging layer that can handle different types of loggers,
including code references, arrays, file paths, and objects.
It also supports logging to syslog if configured.

# METHODS

## new

    my $logger = Log::Abstraction->new(%args);

Creates a new `Log::Abstraction` object.

Clones existing objects with or without modifications.

    my $clone = $logger->new();

The argument can be a hash,
a reference to a hash or the `logger` value.
The following arguments can be provided:

- `config_file`

    Points to a configuration file which contains the parameters to `new()`.
    The file can be in any common format including `YAML`, `XML`, and `INI`.
    This allows the parameters to be set at run time.

- `logger` - A logger can be a code reference, an array reference, a file path, or an object.
- `syslog` - A hash reference for syslog configuration.
- `script_name` - Name of the script, needed when `syslog` is given

## debug

    $logger->debug(@messages);

Logs a debug message.

## info

    $logger->info(@messages);

Logs an info message.

## notice

    $logger->notice(@messages);

Logs a notice message.

## trace

    $logger->trace(@messages);

Logs a trace message.

## warn

    $logger->warn(@messages);
    $logger->warn(\@messages);
    $logger->warn(warning => \@messages);

Logs a warning message. This method also supports logging to syslog if configured.
If not logging mechanism is set,
falls back to `Carp`.

# AUTHOR

Nigel Horne ` <njh@nigelhorne.com` >

# SUPPORT

This module is provided as-is without any warranty.

Please report any bugs or feature requests to `bug-log-abstraction at rt.cpan.org`,
or through the web interface at
[http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Log-Abstraction](http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Log-Abstraction).
I will be notified, and then you'll
automatically be notified of progress on your bug as I make changes.

You can find documentation for this module with the perldoc command.

    perldoc Log::Abstraction

You can also look for information at:

- MetaCPAN

    [https://metacpan.org/dist/Log-Abstraction](https://metacpan.org/dist/Log-Abstraction)

- RT: CPAN's request tracker

    [https://rt.cpan.org/NoAuth/Bugs.html?Dist=Log-Abstraction](https://rt.cpan.org/NoAuth/Bugs.html?Dist=Log-Abstraction)

- CPAN Testers' Matrix

    [http://matrix.cpantesters.org/?dist=Log-Abstraction](http://matrix.cpantesters.org/?dist=Log-Abstraction)

- CPAN Testers Dependencies

    [http://deps.cpantesters.org/?module=Log::Abstraction](http://deps.cpantesters.org/?module=Log::Abstraction)

# COPYRIGHT AND LICENSE

Copyright (C) 2025 Nigel Horne

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.
