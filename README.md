# Lab 2: Publishing RDF Data

## Part 1: Create Your Vocabulary

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>.
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>.

:Person a rdfs:Class;
rdfs:label "person"@en;
rdfs:comment "A person is a human being who is regarded as an individual."@en.

:Country a rdfs:Class;
rdfs:label "country"@en;
rdfs:comment "State or a nation."@en.

:CourseOfStudy a rdfs:Class;
rdfs:label "course of study"@en;
rdfs:comment "A set of classes or a plan of study on a particular subject, usually leading to an exam or qualification."@en.

:Company a rdfs:Class;
rdfs:label "company"@en;
rdfs:comment "A professional organization that acts as an employer and a structured entity for collective work and commercial goals."@en.

:StartUpCompany a rdfs:Class;
rdfs:subClassOf :Company;
rdfs:label "start-up company"@en;
rdfs:comment "A young company founded by one or more entrepreneurs to develop a unique product or service and bring it to market, typically characterized by high innovation and rapid scalability."@en.

:WorkPlace a rdfs:Class;
rdfs:label "work place"@en;
rdfs:comment "Location where a company is based at."@en.

:StartUpHub a rdfs:Class;
rdfs:subClassOf :WorkPlace;
rdfs:label "start-up hub"@en;
rdfs:comment "Special type of work place where start-up companies are gathered."@en.

:City a rdfs:Class;
rdfs:label "city"@en;
rdfs:comment "An urban settlement that serves as a primary geographic container for buildings, organizations, and residents."@en.

:origin a rdf:Property;
rdfs:label "origin"@en;
rdfs:comment "Where a person was born."@en;
rdfs:domain :Person;
rdfs:range :Country.

:familyOrigin a rdf:Property;
rdfs:label "family origin"@en;
rdfs:comment "Where a family originates from."@en;
rdfs:domain :Person;
rdfs:range :Country.

:graduated a rdf:Property;
rdfs:label "graduated"@en;
rdfs:comment "The fact of finishing a degree or other course of study at a university or school."@en;
rdfs:domain :Person;
rdfs:range :CourseOfStudy.

:worksFor a rdf:Property;
rdfs:label "works for"@en;
rdfs:comment "Relates a person to an organization, company, or institution where they are currently employed."@en;
rdfs:domain :Person;
rdfs:range :Company.

:workLocation a rdf:Property;
rdfs:label "work location"@en;
rdfs:comment "Location where a person is working."@en;
rdfs:domain :Person;
rdfs:range :WorkPlace.

:location a rdf:Property;
rdfs:label "location"@en;
rdfs:comment "Location where a company is based at."@en;
rdfs:domain :WorkPlace;
rdfs:range :City.

:basedAt a rdf:Property;
rdfs:label "based at"@en;
rdfs:comment "Location where a company is based at."@en;
rdfs:domain :Company;
rdfs:range :WorkPlace.

:Germany a :Country;
rdfs:label "Germany"@en;
rdfs:comment "Country in central Europe."@en.

:Taiwan a :Country;
rdfs:label "Taiwan"@en;
rdfs:comment "Country in East Asia."@en.

:Gent a :City;
rdfs:label "Gent"@en;
rdfs:comment "A specific instance of a city or administrative area representing Gent, Belgium."@en.

:MasterOfComputerScience a :CourseOfStudy;
rdfs:label "Master of Computer Science"@en;
rdfs:comment "A university degree focused on advanced computing theory, software development, and information systems."@en.

:WinterCircus a :StartUpHub;
rdfs:label "Wintercircus"@en;
rdfs:comment "A specific instance of a technology hub representing the Wintercircus in Ghent, which provides a collaborative ecosystem for entrepreneurs and high-tech organizations."@en;
:location :Gent.

:HydrosyncAi a :StartUpCompany;
rdfs:label "Hydrosync.ai"@en;
rdfs:comment "A specific instance of a the start-up company representing the organization hydrosync.ai, who is focusing on accelerating the decarbonization of buildings by utilizing IoT sensor networks and AI-driven insights to optimize indoor climate comfort and reduce energy waste."@en;
:basedAt :WinterCircus.

:Anna a :Person;
rdfs:label "Anna"@en;
rdfs:comment "An individual record representing the personal, educational, and cultural background of Anna."@en;
:origin :Germany;
:familyOrigin :Taiwan;
:graduated :MasterOfComputerScience;
:worksFor :HydrosyncAi;
:workLocation :WinterCircus.

