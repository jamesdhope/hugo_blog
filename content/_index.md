---
# Leave the homepage title empty to use the site title
title: 'James Hope'
date: 2022-10-24
type: landing

sections:
  - block: about.biography
    id: about
    content:
      title: 
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
  - block: experience
    content:
      title: Recent Experience
      # Date format for experience
      #   Refer to https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Experiences.
      #   Add/remove as many `experience` items below as you like.
      #   Required fields are `title`, `company`, and `date_start`.
      #   Leave `date_end` empty if it's your current employer.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - title: Senior Solutions Architect
          company: IBM
          company_url: ''
          company_logo: ibm
          location: United Kingdom
          date_start: '2023-04-01'
          date_end: ''
          description: |2-
              Building a lot more next generation AI.
        - title: Solutions Architect
          company: IBM
          company_url: ''
          company_logo: ibm
          location: United Kingdom
          date_start: '2022-01-01'
          date_end: '2023-04-01'
          description: |2-
              Building next generation AI, digital twins, event driven integrations, automations and hybrid cloud infrastructure.
        - title: Academic Tutor
          company: University of London
          company_url: ''
          company_logo: uol
          location: United Kingdom
          date_start: '2011-01-01'
          date_end: '2021-12-01'
          description: Teaching Machine Learning
        - title: Software Engineer
          company: Various inc. Barclays, HSBC, BP, Cancer Research, Wellcome Trust
          company_url: ''
          company_logo: 
          location: United Kingdom
          date_start: '2010-12-01'
          date_end: '2005-10-01'
          description: Building technology for predictive maintenance; building and deploying cloud native apps; a lot of kubernetes and configuration of service meshes; deploying observability stacks, DevSecOps toolchains, amongst other things.
    design:
      columns: '2'
  - block: accomplishments
    content:
      # Note: `&shy;` is used to add a 'soft' hyphen in a long heading.
      title: 'Education'
      subtitle: 
      # Date format: https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `item` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - certificate_url: https://google.accredible.com/1955e0c9-5991-4308-b915-42274832908a
          date_end: '2004-08-01'
          date_start: '2001-09-01'
          description: 'First Class with Honours'
          icon: swansea
          organization: Swansea University
          organization_url: https://cloud.google.com/
          title: Computer Science BSc
          url: ''
        - certificate_url: https://google.accredible.com/4804f5ce-eb49-4898-acb3-530c732c7955
          date_end: '2005-08-01'
          date_start: '2004-09-01'
          description: 'Applications of cryptography in association with Cambridge Department of Computer Science and Bletchley Park'
          icon: cambridge
          organization: Cambridge University
          organization_url: https://cloud.google.com/
          title: International Relations MPhil
          url: ''
    design:
      columns: '2'
  - block: accomplishments
    content:
      # Note: `&shy;` is used to add a 'soft' hyphen in a long heading.
      title: 'Certifications'
      subtitle:
      # Date format: https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `item` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - certificate_url: https://google.accredible.com/1955e0c9-5991-4308-b915-42274832908a
          date_end: ''
          date_start: '2023-07-29'
          description: ''
          icon: gcp
          organization: Google Cloud
          organization_url: https://cloud.google.com/
          title: Professional Machine Learning Engineer
          url: ''
        - certificate_url: https://google.accredible.com/4804f5ce-eb49-4898-acb3-530c732c7955
          date_end: ''
          date_start: '2023-07-29'
          description: ''
          icon: gcp
          organization: Google Cloud
          organization_url: https://cloud.google.com/
          title: Professional Cloud Architect
          url: ''
        - certificate_url: https://www.credly.com/badges/6aecdeae-820a-446e-9f90-8c2422e0defb/public_url
          date_end: ''
          date_start: '2023-05-01'
          description: ''
          icon: ibm
          organization: IBM
          organization_url: https://www.coursera.org
          title: IBM Certified Architect
          url: ''
        - certificate_url: https://www.credly.com/badges/5a507977-8bf7-4ada-89f7-fa8b4bf47c06?source=linked_in_profile
          date_end: ''
          date_start: '2021-01-25'
          description: ''
          icon: cissp
          organization: IBM
          organization_url: https://www.isc2.org/
          title: Certified Information Systems Security Professional (CISSP)
          url: ''
        - certificate_url: https://www.credly.com/badges/68e8a8fe-74e8-4925-89be-5c2ddbad65f0/public_url
          date_end: ''
          date_start: '2022-04-01'
          description: ''
          icon: rh
          organization: Red Hat
          organization_url: https://www.redhat.com/en
          title: Red Hat Certified OpenShift Administrator
          url: ''
        - certificate_url: https://credentials.edx.org/credentials/a6dc1b11b357459f82c37c3f7ab7c32b/
          date_end: ''
          date_start: '2019-02-01'
          description: ''
          icon: harvardx
          organization: HarvardX
          organization_url: https://www.edx.org/certificates/professional-certificate/harvardx-data-science
          title: Certified Data Scientist
          url: ''
        
        
    design:
      columns: '2'
  - block: collection
    id: posts
    content:
      title: Recent Posts
      subtitle: ''
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        folders:
          - post
        author: ""
        category: ""
        tag: ""
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: compact
      columns: '2'
  #- block: portfolio
  #  id: projects
  #  content:
  #    title: Projects
  #    filters:
  #      folders:
  #        - project
  #    # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
  #    default_button_index: 0
  #    # Filter toolbar (optional).
  #    # Add or remove as many filters (`filter_button` instances) as you like.
  #    # To show all items, set `tag` to "*".
  #    # To filter by a specific tag, set `tag` to an existing tag name.
  #    # To remove the toolbar, delete the entire `filter_button` block.
  #    buttons:
  #      - name: All
  #        tag: '*'
  #      - name: Deep Learning
  #        tag: Deep Learning
  #      - name: Other
  #        tag: Demo
  #  design:
  #    # Choose how many columns the section has. Valid values: '1' or '2'.
  #    columns: '1'
  #    view: showcase
  #    # For Showcase view, flip alternate rows?
  #    flip_alt_rows: false
  #- block: markdown
  #  content:
  #    title: Gallery
  #    subtitle: ''
  #    text: |-
  #      {{< gallery album="demo" >}}
  #  design:
  #    columns: '1'
  #- block: collection
  #  id: featured
  #  content:
  #    title: Featured Publications
  #    filters:
  #      folders:
  #        - publication
  #      featured_only: true
  #  design:
  #    columns: '2'
  #    view: card
  #- block: collection
  #  content:
  #    title: Recent Publications
  #    text: |-
  #      {{% callout note %}}
  #      Quickly discover relevant content by [filtering publications](./publication/).
  #      {{% /callout %}}
  #    filters:
  #      folders:
  #        - publication
  #      exclude_featured: true
  #  design:
  #    columns: '2'
  #    view: citation
  #- block: collection
  #  id: talks
  #  content:
  #    title: Recent & Upcoming Talks
  #    filters:
  #      folders:
  #        - event
  #  design:
  #    columns: '2'
  #    view: compact
  - block: tag_cloud
    content:
      title: Popular Topics
    design:
      columns: '2'
  #- block: contact
  #  id: contact
  #  content:
  #    title: Contact
  #    subtitle:
  #    text: |-
  #      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam mi diam, venenatis ut magna et, vehicula efficitur enim.
      # Contact (add or remove contact options as necessary)
      #email: test@example.org
      #phone: 888 888 88 88
      #appointment_url: 'https://calendly.com'
      #address:
      #  street: 450 Serra Mall
      #  city: Stanford
      #  region: CA
      #  postcode: '94305'
      #  country: United States
      #  country_code: US
      #directions: Enter Building 1 and take the stairs to Office 200 on Floor 2
      #office_hours:
      #  - 'Monday 10:00 to 13:00'
      #  - 'Wednesday 09:00 to 10:00'
      # Choose a map provider in `params.yaml` to show a map from these coordinates
      #coordinates:
      #  latitude: '37.4275'
      #  longitude: '-122.1697'  
      #contact_links:
      #  - icon: twitter
      #    icon_pack: fab
      #    name: DM Me
      #    link: 'https://twitter.com/Twitter'
      #  - icon: skype
      #    icon_pack: fab
      #    name: Skype Me
      #    link: 'skype:echo123?call'
      #  - icon: video
      #    icon_pack: fas
      #    name: Zoom Me
      #    link: 'https://zoom.com'
      # Automatically link email and phone or display as text?
      #autolink: true
      # Email form provider
      #form:
      #  provider: netlify
      #  formspree:
      #    id:
      #  netlify:
      #    # Enable CAPTCHA challenge to reduce spam?
      #    captcha: false
    #design:
    #  columns: '2'
---
