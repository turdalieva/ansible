# ansible
ansible repository
- name: 'Install dependencies'
  include_tasks: 'vmware_install.yml'
  loop: "{{ vmware_deps['results'] }}"
  when:
    - item.not_found | length != 0
    - vsphere_install_sdk
