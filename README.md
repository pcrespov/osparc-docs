## Executive Summary

This document provides a detailed update on Deliverable D1.1 "Detailed technical 
specifications for o2S2PARC, based on user requirements (e.g., from questionnaires) and 
technology evaluation" of the IT'IS SIM-CORE proposal.

The specifications for the SIM-CORE platform (o2S2PARC) were established through two 
separate activities: (i) contacting SPARC teams to establish their specific modeling needs 
(primarily by detailed interviews) and (ii) evaluating the best suited software technologies for 
a high-quality implementation of the SIM-CORE.  The assessment of the software 
technologies was achieved by the comparison of various feasibility prototypes which were 
developed with different technologies. Deliverable D.1.1 and the related Milestones to this 
deliverable, M1.1, M1.2, and M1.3, have now been completed. As a result, high-level 
platform functionality specifications and concrete framework architecture specifications were 
derived that are summarized in this document. 

Overall, the willingness of the SPARC teams to participate in interviews and to discuss team-
specific needs and requirements was high. We have experienced large enthusiasm about 
both the possibility of sharing own models without the need to invest in developing user-
interface functionality and the potential of getting access to powerful solvers, meta-
modeling functionality, electrophysiology models, and analysis tools. Quality assurance 
aspects, data and model integration, user-friendliness, computational infrastructure, 
anatomical models, and support for workflows are other highly valued components. The 
platform concept, as originally developed throughout the SIM-CORE application process, is 
very well suited to meet these requirements, and only few extensions of the original 
proposal are required. These include: (i) support for "supercomputing", workflows, nerve 
microstructure modeling, thermal, biomechanical, and light propagation modeling (IT'IS does 
not have solvers for the latter two and would have to develop them), (ii) machine learning, 
(iii) additional animal anatomical models, as well as a detailed spinal cord model, (iv) 
modeling of fields generated by neural activity for sensing, and (v) further meta-modeling 
(control, model order reduction. At this point, other aspects do not seem to be of high 
priority for the SPARC teams (e.g., image-processing beyond segmentation and functionality 
for users to implement their own, advanced-interaction GUI-elements). Providing users with 
proper support will be fundamental to assure the widespread adoption of the platform.

As mentioned above, all of the requirements are very much aligned with our prior 
expectations and only a minor adaptation of the proposal is required. We propose, however, 
an additional sub-project to support the SPARC teams in adopting the SIM-CORE platform. 
We would further consider to add some of the proposed extensions (see above) after 
detailed discussions with the SPARC office. Furthermore, we propose to implement 
Deliverable 6.4 (development of functionality to allow users to create UIs for their services) 
with increased priority - to allow faster SPARC-team model integration - while delaying the 
implementation of high-level Python scripting interfaces (D6.1/6.2), user-defined viewer 
plug-ins (D5.4), and advanced image-based nerve tracing (D3.3).

Our evaluation of existing software technologies resulted in clear favorites for the 
technologies and approaches to be used for implementing the SIM-CORE platform. These 
are: (i) a front-end built with [qooxdoo], (ii) a python-based web-server, and (iii) a swarm of 
pipelined computational services deployed inside dockers and (iv) orchestrated by a director 
that is in turn interacting with the web server. This design provides the SIM-CORE with 
sustainable capabilities that enable scientists to share their computational models in 
dedicated environments with minimal adaptation effort while providing at the same time the 
capability to build workflows with other scientist's models and an attractive interface to 
established models/services.  

The planned design of the
platform will enable maximal flexibility with regard to the wide variety
of existing and envisioned user-generated modeling services. It will also 
offer user-friendly interfaces, allowing users to engage on different
levels with the platform, ranging from simple execution of existing
models to the advanced generation of services with fine-grained control
over dedicated user-interface elements, depending on expertise. Due to
the modularity of the chosen approach, it will be simple to extend and
adapt the platform at later time-points, and it will be feasible to
revisit some of the choices as technology evolves and to replace layers
or components of the implementation without the need for a complete
redesign of the platform.



## Introduction
This document reports on Deliverable D1.1, "Detailed technical specifications for o2S2PARC, 
based on user requirements (e.g., from questionnaires) and technology evaluation", of the 
IT'IS SIM-CORE proposal. 
Deliverable D.1.1 and the related Milestones M1.1, M1.2, and M1.3 have been completed. 
After presenting the [requirement gathering approach and
effort](./reqs/methodology.md), the [obtained information is
summarized](./reqs/results.md), and [conclusions](./reqs/conclusions.md)
are drawn. The [technology evaluation approach and
activities](./tech/intro.md) are introduced, [results](./tech/intro.md)
are presented, and [conclusions](./tech/conclusion.md) are reached. From
this, [high level platform functionality specifications](./specs/high-level.md) 
and [framework architecture specifications](./specs/low-level.md) are derived.