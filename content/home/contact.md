---
# An instance of the Contact widget.
widget: contact

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 130

title: Contact
subtitle:

content:
  # Automatically link email and phone or display as text?
  autolink: true

  # Email form provider
  form:
    provider: netlify
    formspree:
      id:
    netlify:
      # Enable CAPTCHA challenge to reduce spam?
      captcha: false

  # Contact details (edit or remove options as required)
  email: federico.dallo.1989@gmail.com
  phone: 888 888 88 88
  address:
    street: 390 Wurster Hall
    city: Berkeley
    region: CA
    postcode: '94720'
    country: United States
    country_code: US
  coordinates:
    latitude: '37.8700'
    longitude: '-122.2555'
  directions: Enter Building and take the stairs to Office 390 on Floor 3
  office_hours:
    - 'Monday 10:00 to 12:00'
    - 'Tuesday 10:00 to 12:00'
  appointment_url: 'https://calendly.com'
  contact_links:
    - icon: twitter
      icon_pack: fab
      name: DM Me
      link: 'https://twitter.com/Twitter'
    - icon: video
      icon_pack: fas
      name: Zoom Me
      link: 'https://zoom.com'

design:
  columns: '2'
---
