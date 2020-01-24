## WinRM::WinRSExec

WinRM Perl module.

WinRM::WinRSExec - Connects with Windows Machines running WinRM.

Based on **curl** runs remote commands using Windows Remote Shell (WinRS)

### Usage:

<pre>
use WinRM::WinRSExec;

my $winrm = WinRM::WinRSExec->new({
    host            => "WINDOWSADSERVER",
    protocol        => "http",
    timeout         => 60,
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
print "STD LOG:\n" . $winrm->logger . "\n";    # Optional use
</pre>

### Features

- Supports HTTP protocol.

- Supports HTTPS protocol.

- Supports Basic Authentication.

- Supports Negotiate Authentication (Kerberos, NTLM).
