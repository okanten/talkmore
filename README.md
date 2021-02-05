# Talkmore

Uses requests to interact with the talkmore web interface.

Allows for sending sms, sending sms to all registered contacts, as well as retrieving contacts, and adding contacts.

## Examples

```python
talkmore = Talkmore('phone_number', 'password')
talkmore.login()
talkmore.send_sms('receiver', 'message')

# Contacts
contacts = talkmore.get_contacts()
talkmore.add_contact('first_name', 'last_name', 'phone_number')
talkmore_as = talkmore.find_contact_id_by_phone_number('91509915')
talkmore.delete_contact(talkmore_as)

# Delete multiple contacts
contacts = ['91509915', '02800']
talkmore.delete_contacts(contacts)

# Send sms to multiple numbers
contacts = ['91509915', '02800']
talkmore.send_sms(contacts, 'message')

# Send sms to all contacts
talkmore.send_sms_to_all_contacts('message')

# Alternatively, include yourself
talkmore.send_sms_to_all_contacts('message', send_to_self=True)

```


