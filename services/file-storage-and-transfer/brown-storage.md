---
title: Brown Storage Options
icon: database
---

Several services at Brown allow you to share and store files. These different 
storage services each have their own relative benefits and features. You can 
explore the differences with our comparison tool using the link below.

<details>
    <summary>Campus File Storage Non-replicated / Research Services</summary>
    <p>
        File Services for Research provides Brown University research departments 
        with a location in which files can be stored, backed up, and shared with members 
        of the Brown community using Brown ID’s and groups. Space is allocated to each 
        research lab or PI with an ITHelp request , security groups are required to define 
        access to the data. The data is protected locally via snapshots but doesn’t have 
        geo-redundancy (secondary copy).
    </p>
    <ul>
        <li>
            Best for: Brown faculty and staff researchers looking to store, share and 
            protect research data.
        </li>
        <li>
            Accessibility: The data is accessible on Brown's campus networks (including 
            VPN and wireless). Also accessible directly from High Performance Computing 
            Cluster (Oscar).
        </li>
        <li>
            Sharing: The data can be shared with both Brown and non-Brown collaborators 
            via Globus.
        </li>
        <li>Limitations: No geo-redundancy (secondary copy)</li>
        <li>Rate: $50/TB/Year when storing above free/grant allocations</li>
    </ul>
</details>

<details>
    <summary>Campus File Storage Replicated / Research Services</summary>
    <p>
        File Services for Research provides Brown University research departments 
        with a location in which files can be stored, backed up, and shared with 
        members of the Brown community using Brown ID’s and groups. Space is allocated 
        to each research lab or PI with an ITHelp request , security groups are 
        required to define access to the data. The data is replicated daily to our 
        disaster recovery site for True geo-redundant data protection. The data is
        accessible on Brown's campus networks (including VPN and wireless).
    </p>
    <ul>
        <li>
            Best for: Brown faculty and staff researchers looking to store, share and
            protect research data.
        </li>
        <li>
            Accessibility: The data is accessible on Brown's campus networks (including 
            VPN and wireless). Also accessible directly from High Performance Computing 
            Cluster (Oscar).
        </li>
        <li>
            Sharing: The data can be shared with both Brown and non-Brown collaborators 
            via Globus.
        </li>
        <li>Rate: $100/TB/Year when storing above free/grant allocations</li>
    </ul>
</details>

<details>
    <summary>Campus File Storage / Department File Services</summary>
    <p>
        Departmental File Services provides University departments with a location in which 
        files can be stored, backed up, and shared across the department. The service can be 
        accessed by mapping the drive on your computer (
        <a href="https://ithelp.brown.edu/kb/articles/38-connect-to-departmental-file-services-on-windows">Windows Explorer</a>
        on PC or <a href="https://ithelp.brown.edu/kb/articles/3-connect-to-department-file-services-with-mac-osx">Finder</a> 
        on a Mac), or by visiting <a href="http://webfiles.brown.edu/">webfiles.brown.edu</a> 
        in a web browser. (For researchers, please check out "Campus File Storage 
        replicated/non-replicated / Research services " section)
    </p>
    <ul>
        <li>
            Best for: Backing up and sharing official department documents, ensuring longevity
            of documents after file authors leave Brown.
        </li>
        <li>
            Limitations: Can only be accessed on the Brown network or with VPN. Not as easy to 
            access as consumer services (no app, web access is a bit clunky). Sharing is not 
            easy: no sharing with people outside of Brown, no sharing with people who don't
            have access to the department folders. 
        </li>
        <li>
            More info: <a href="https://ithelp.brown.edu/kb/37-department-file-services">Documentation</a>
        </li>
    </ul>
    
</details>

<details>
    <summary>Oscar Storage</summary>
    <p>
        Oscar storage also known as Computational Data Storage is a high-performance 
        data storage system which is accessible from any computer connected to Brown's 
        campus network, or from outside the network via ssh. What sets this option apart 
        from the others is that it is directly connected to Brown’s primary supercomputer, 
        “Oscar”, making computation easier. If you don’t intend to compute your data with 
        Brown’s supercomputer, you may consider using Campus File Storage instead. You could 
        also use Oscar storage for computing and then move your results to Campus File Storage 
        for greater accessibility, reliability, and protection.
    </p>
    <ul>
        <li>Synonyms: Oscar Data, HPC Storage, GPFS (historically)</li>
        <li>
            Best for: High performance storage of research data, perform computation on 
            your data using Brown’s supercomputer
        </li>
        <li>Limitations: Not accessible on all campus networks.</li>
        <li>Rate: $100/TB/Year when storing above free/grant allocations</li>
        <li>
            More info: 
            <a href="https://ccv.brown.edu/services/computing#high-performance-computing-(oscar)">Documentation</a> | 
            <a href="https://brown.co1.qualtrics.com/jfe/form/SV_0GtBE8kWJpmeG4B">Request these services</a>
        </li>
    </ul>
</details>

<details>
    <summary>Stronghold</summary>
    <p>
        <a href="https://it.brown.edu/services/stronghold-research-environment-data-compliance">Stronghold</a> 
        is a secure computing and storage environment that enables Brown researchers to analyze sensitive data 
        while complying with regulatory or contractual requirements.
    </p>
    <ul>
        <li>Best for: Storing data with data usage agreements, FISMA, etc.</li>
        <li>Rate: $100/TB/Year when storing above free/grant allocations</li>
        <li>More info: <a href="https://www.brown.edu/cis/forms/Stronghold/shold.php">Request this service</a></li>
    </ul>
</details>

<details>
    <summary>Hibernate</summary>
    <p>
        <a href="https://docs.ccv.brown.edu/hibernate/">Hibernate</a> is a secure, reliable,
        research data archive solution. Hibernate is a Brown OIT archival service for the 
        research community to migrate inactive data off active Network-attached storage (NAS)
        platforms onto a lower cost, long-term retention environment.
    </p>
    <ul>
        <li>
            Hibernate leverages <a href="https://docs.ccv.brown.edu/starfish/">StarFish</a> 
            an application that provides a metadata and rules-based 
            management framework for large file systems. StarFish makes storage tiering easy: 
            moving data, reporting, zones.
        </li>
    </ul>
</details>

<details>
    <summary>Lab Archives</summary>
    <p>
        LabArchives is a cloud-based electronic lab notebook that can be used by researchers, 
        instructors, and students for input and organization of laboratory data, information 
        sharing, and collaboration, and for saving historical versions of files. It is appropriate 
        for use in a wide variety of laboratories, including biological sciences, chemistry and 
        physical sciences, and engineering, among others.
    </p>
    <p>
        LabArchives at Brown provides unlimited storage space. The current size limit per file is 4GB.
    </p>
    <p>
        LabArchives at Brown is not approved for storing files containing Personally Identifiable 
        Information (PII), Protected Health Information (PHI), or Brown Restricted Information.
    </p>
    <ul>
        <li>More info: <a href="https://library.brown.edu/info/labarchives/">Documentation</a></li>
    </ul>
</details>

<details>
    <summary>Brown Digital Library</summary>
    <p>
        The Brown Digital Repository (BDR) is a place to gather, index, store, preserve, and make 
        available digital assets produced via the scholarly, instructional, research, and administrative 
        activities at Brown.
    </p>
    <p>The Brown University Library maintains the repository as a service to the Brown community; it provides:</p>
    <ul>
        <li>A searchable index of digital objects shared by the Brown community.</li>
        <li>Permanent, secure storage for personal and departmental digital objects.</li>
        <li>Off-site backups of digital content.</li>
        <li>Tools for sharing and publishing digital content.</li>
        <li>Data curation, format migration, and preservation services.</li>
    </ul>
    <p>
        Faculty and researchers interested in using the Brown Digital Repository as a platform for 
        programmatic data management, storage, and publication should contact the Library (bdr@brown.edu) 
        for information about opportunities for research consulting and project development support.
    </p>
    <ul>
        <li>More info: <a href="https://repository.library.brown.edu/studio/about/">Documentation</a></li>
    </ul>
</details>

<details>
    <summary>Google Drive</summary>
    <p>
        Google Drive gives you space to store and share documents. The native Google document 
        formats allow for real-time collaboration and file history. You can also store unconverted files 
        of various types in your Google Drive. It's easy to share files with members of the Brown community 
        (including Google Groups) and non-Brown Google accounts; files can be shared with view-only, comment, 
        or edit access. Google also has a really nice feature where you can scan in handwritten documents and 
        have them converted to text. You can access files on the web, through a mobile app, or by installing 
        Google Drive on your computer (which makes it act like a folder on your computer).
    </p>
    <ul>
        <li>
            Best for: Collaboration in native Google files, easy access from anywhere, small amount of total
            storage, sharing with Google Groups.
        </li>
        <li>
            Limitations: Data transfer speeds may be very limited, Globus can provide high bandwidth data transfers.
        </li>
        <li>
            More info: <a href="https://ithelp.brown.edu/kb/48-google-drive">Documentation</a>
            | <a href="https://storage.googleapis.com/gfw-touched-accounts-pdfs/google-cloud-security-and-compliance-whitepaper.pdf">Security</a>
        </li>
    </ul>
</details>
<br/>
<p>
    <a href="/storage" class="button is-link">Compare Storage Options</a>
    <a href="https://brown.atlassian.net/servicedesk/customer/portal/16/group/55/create/218" class="button is-link">Request Storage</a>
    <a href="https://brown.atlassian.net/servicedesk/customer/portal/16/group/55/create/219" class="button is-link">Request Quota Increase</a>
    <a href="https://brown.atlassian.net/servicedesk/customer/portal/16/group/55/create/217" class="button is-link">Storage Help</a>
</p>
