# Ansible Role: NTP

This role installs and configures NTP on RHEL/CentOS, Debian/Ubuntu and Fedora servers.

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: foobar
      roles:
        - role: ansible-role-ntp
          become: yes

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    ntp_driftfile: /var/lib/ntp/drift

Configure the drift file for ntp.

    ntp_server:
      - 0.de.pool.ntp.org
      - 1.de.pool.ntp.org
      - 2.de.pool.ntp.org
      - 3.de.pool.ntp.org

Configure servers for ntp.

    ntp_restrict:
      - "restrict -4 default kod notrap nomodify nopeer noquery"
      - "restrict -6 default kod notrap nomodify nopeer noquery"
      - "restrict 127.0.0.1"

Configure restrictions for ntp.

    ntp_includefile: no

Configure includefile for ntp.

    ntp_statistics: no

Configure statistics for ntp.

## Dependencies

None.

## Example Playbook

    - hosts: foobar
      become: yes
      roles:
        - ansible-role-ntp

## Contributing

Please feel free to open issues if you find any bugs, problems or if you see room for improvement. Also feel free to contact me anytime if you want to ask or discuss something.

## Disclaimer

This role is provided AS IS and I can and will not guarantee that the role works as intended, nor can I be accountable for any damage or misconfiguration done by this role. Study the role thoroughly before using it.

## License

GPLv3

## Author Information

This role was created in 2019 by [Thorian93](https://thorian93.de/).