# wc-iac

to pull configuration on a windows client

1. install puppet client
> Download 64-bit from https://downloads.puppetlabs.com/windows/puppet-agent-x64-latest.msi
> or Download 32-bit from https://downloads.puppetlabs.com/windows/puppet-agent-x86-latest.msi
> Install String: msiexec /qn /norestart /i puppet-agent-<VERSION>-<x86/x64>.msi

2. install github client
> Download latest from https://git-for-windows.github.io/
> or use "choco install git"

3. clone puppet configuration
 open command prompt
> c:
> cd \ProgramData\Git
> git clone https://github.com/benikaj/wc-iac.git

4. use windows task manager, wmic, or rdp to start the puppet in ad hoc evaluation mode
> puppet -v c:\ProgramData\Git\wc-iac\manifests\site.pp --modulepath=c:\ProgramData\Git\wc-iac\modules
# C:
# cd \ProgramData\Git\wc-iac
puppet apply -v "C:\ProgramData\Git\wc-iac\manifests\site.pp" --modulepath="C:\ProgramData\Git\wc-iac\modules"

5. (optional) uninstall puppet client
> msiexec /qn /norestart /x puppet-agent-<VERSION>-<x86/x64>.msi
