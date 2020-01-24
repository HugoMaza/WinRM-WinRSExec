## WinRM-WinRSExec

WinRM Perl module.

WinRM::WinRSExec - Connects with Windows Machines running WinRM.
Based on CURL runs remote commands using Windows Remote Shell (WinRS)

Usage mode:

<pre>
use WinRM::WinRSExec;

my $winrm = WinRM::WinRSExec->new({
    host            => "WINDOWSADSERVER",
    protocol        => "http",
    timeout	        => 60,
    domain          => 'DOMAIN.LOCAL',
    username        => 'mi.AD.user',
    password        => 'mYp4ssw0rd',
    kerberos        => 1
});

my $command = 'PowerShell -Command "&{Get-Host;}"';

$winrm->execute({
    command => $command
});

print "STD OUT:\n" . $winrm->response . "\n";
print "STD ERR:\n" . $winrm->error . "\n";
</pre>

### Features

- item * Supports HTTP protocol.

- item * Supports HTTPS protocol.

- item * Supports Basic Authentication.

- item * Supports Kerberos Authentication.
