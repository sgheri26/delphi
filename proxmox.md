# Proxmox guide

## Proxmox post-setup

1. Disable lid sleep configurations

    - Add "ignore" to the lines below from file **/etc/systemd/logind.conf**

        - HandleLidSwitch=ignore

        - HandleLidSwitchDocked=ignore

        - HandleLidSwitchExternalPower=ignore


        > ```bash
        > nano /etc/systemd/logind.conf
        > ```


 
    - After editing logind.conf restart service systemd-logind

        > ```bash
        > systemctl restart systemd-logind
        > ```


    - You can also disable suspend/hibernation all togheter

        > ```bash
        > systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
        > ```

        - If you need to revert

            > ```bash
            > systemctl unmask sleep.target suspend.target hibernate.target hybrid-sleep.target
            > ```

