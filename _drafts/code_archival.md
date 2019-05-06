# Archival and citation of code and data

In many areas of modern research, academic papers form only a part of scholarly output and they frequently do not contain enough information for reproducibility and detailed academic discourse. A more complete description of the research additionally requires the publication of computer code, software version information and supporting data files.

Publication of academic code and data is becoming increasingly common but there are currently no generally accepted standards for *where* and *how* these research objects should be published. Despite obvious shortcomings [1] it is common practice to upload code and data to personal websites that often disappear after a relatively short time.  Even the more modern practice of linking to GitHub repositories are insufficient because there is no guarantee of permanence.

When considering where to publish code and data, we refer to the six principles of software citation taken from [2]:

1. **Importance**: Software should be considered a legitimate and citable product of research. Software citations should be accorded the same importance in the scholarly record as citations of other research products, such as publications and data; they should be included in the metadata of the citing work, for example in the reference list of a journal article, and should not be omitted or separated. Software should be cited on the same basis as any other research product such as a paper or a book, that is, authors should cite the appropriate set of software products just as they cite the appropriate set of papers.
2. **Credit and attribution**: Software citations should facilitate giving scholarly credit and normative, legal attribution to all contributors to the software, recognizing that a single style or mechanism of attribution may not be applicable to all software.
3. **Unique identification**: A software citation should include a method for identification that is machine actionable, globally unique, interoperable, and recognized by at least a community of the corresponding domain experts, and preferably by general public researchers.
4. **Persistence**: Unique identifiers and metadata describing the software and its disposition should persist even beyond the lifespan of the software they describe.
5. **Accessibility**: Software citations should facilitate access to the software itself and to its associated metadata, documentation, data, and other materials necessary for both humans and machines to make informed use of the referenced software.
6. **Specificity**: Software citations should facilitate identification of, and access to, the specific version of software that was used. Software identification should be as specific as necessary, such as using version numbers, revision numbers, or variants such as platforms. 

To work towards satisying these principles, we recommend the use of [Zenodo](https://zenodo.org/) when publishing code and data. Zenodo is a free (for most usage) service, developed by CERN, that is available to researchers from all fields. Software and data deposited with Zenodo is provided with a globally unique Digital Object Identifier (DOI) and its storage is guaranteed for a long period of time. If used in association with GitHub, Zenodo automatically records information such as authorship and software version.
Combined, these features help ensure that all the software citation principles can be met for many use cases.

A workshop on how and why to use Zenodo was delivered as part of a British Ecological Society 2016 meeting and self-paced teaching materials are available from [3].

## References
[1] **Scholarly Context Not Found: One in Five Articles Suffers from Reference Rot**, Klein et al, https://doi.org/10.1371/journal.pone.0115253

[2] **Software citation principles**, Smith et al, https://doi.org/10.7717/peerj-cs.86

[3] **Code publication and citation**, Croucher et al, https://doi.org/10.5281/zenodo.801586
