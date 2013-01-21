# LKIF Core

The LKIF core legal ontology is a library of ontologies relevant for the legal domain. It consists of 15 modules, each of which describes a set of closely related concepts from both legal and commonsense domains.

<h3>Abstract Concepts</h3>

The most abstract concepts are defined in five closely related modules: top, place, mereology, time and spacetime.<br/>

<ul>
	<li><strong>top</strong> The LKIF top ontology is largely based on the top-level of LRI-Core but has less ontological commitment in the sense that it imposes less restrictions on subclasses of the top categories.  </li>
	<li><strong>place</strong> The place module partially implements the theory of relative places (Donnelly, 2005) in OWL DL.</li>
	<li><strong>mereology</strong> The mereology module defines mereological concepts such as parts and wholes, and typical mereological relations such as part of, component of, containment, membership etc.</li>
	<li><strong>time</strong> The time module provides an OWL DL implementation of the theory of time by Allen (1984).</li>
	<!-- ><li><strong>spacetime</strong> The space-time module is a placeholder for the place and time modules.  </li> -->
</ul>

<h3>Basic Concepts</h3>
Basic-level concepts are distributed across four modules: process, role, action and expression.<br/>

<ul>
	<li><strong>process</strong> The process module extends the LKIF top ontology module with a definition of changes, processes (being causal changes) and physical objects. It introduces a limited set of properties for describing participant roles of processes. </li>
	<li><strong>role</strong> The role module defines a typology of roles (epistemic roles, functions, person roles, organisation roles) and the plays-property for relating a role filler to a role.</li>
	<li><strong>action</strong> The action module describes the vocabulary for representing actions in general. Actions are processes which are performed by some agent (the actor of the action). This module does not commit itself to a particular theory on thematic roles. </li>
	<li><strong>expression</strong> The expression module describes a vocabulary for describing, propositions and propositional attitudes (belief, intention), qualifications, statements and media. It furthermore extends the role module with a number or epistemic roles, and is the basis for the definition of norms.</li>
</ul>

<h3>Legal Concepts</h3>
These basic clusters are extended by three modules that form the legal ontology: legal action, legal role and norm.<br/>

<ul>
	<li><strong>legal-action</strong> The legal action module extends the action module with a number of legal concepts related to action and agent, such as public acts, public bodies, legal person, natural person etc.</li>
	<li><strong>legal-role</strong> The legal role module extends the role module with a small number of legal concepts related to roles, legal professions etc.</li>
	<li><strong>norm</strong> The norm module is an extension primarily on the expression module where norms are defined as qualifications. Please refer to Deliverable 1.1 for a more in-depth description of the underlying theory. It furthermore defines a number of legal sources, e.g. legal documents, customary law etc., and a typology of rights and powers, cf. Sartor (2006), Rubino et al. (2006)</li>
</ul>


<h3>Framework Modules</h3>
In addition to these legal clusters, two modules are provided that cover the basic vocabulary of two frameworks: modification and rules.<br/>

<ul>
	<li><strong>modification</strong> The modification module is both an extension of the time module and the legal action module. The time module is extended with numerous intervals and moments describing the efficacy and being in force of legal documents. The action module is extended with a typology of modifications. These concepts are described in further detail in Deliverable 3.2 of the ESTRELLA project.</li>
	<li><strong>rules</strong> The rules &amp; argumentation module defines roles central to argumentation, and describes the vocabulary for LKIF rules as defined in Deliverable 1.1, chapter 5. The module leaves room for further extension to complex argumentation frameworks (AIF, Carneades). </li>
</ul>

<h3>Core and Extended Ontology</h3>
Finally, the twelve modules of the abstract, basic and legal level are integrated in the <strong>LKIF Core</strong> ontology module. This module does not provide any additional definitions, but functions as an entry-point for users of the ontology library. 

The two framework modules are accessible through the <strong>LKIF Extended</strong> ontology module. This module imports the <strong>LKIF Core</strong> module.</p>


## Release notes

### Version 1.1 - 20080722 - Major Changes Release

* Added Subjective_Entity class, and accompanying functional counts_as and imposed_on properties.
* Refined definition of Role classes
* Redefined summarisation properties for Propositional Attitude (e.g. Belief <-> believes/believed_by)
* Added Mental and Physical processes

### Version 1.0.3 - 20080501 - Minor Bugfix Release

* Moved time-modification.owl and lkif-rules.owl modules to new 'lkif-extended.owl' module due to performance hog. These modules are primarily provided for compatibility reasons with e.g. the Metalex/CEN initiative and the LKIF Rules RDF syntax.
* Corrected typo in property immediatly_before -> immediately_before


### Version 1.0.2 - 20070322 - Major Bugfix Release

* Fixed duplicate class definitions in expression module (problem with Jena backend).
* Properties
	* Swapped domain/range on participant/participant_in (!)
	* evaluatively_comparable is now symmetric
	* Separated 'evaluates' from 'qualifies', evaluates is a subproperty of qualifies which relates an Evaluative Attitude to an Evaluative Proposition. The qualifies property is reserved for Qualification and Qualified.
	* Separated 'qualitatively_comparable' from 'evaluatively_comparable'. The former is a superproperty of the latter. The 'normatively_comparable' is also a subproperty of the former.
	* Member property was mistakenly transitive
	* Added strict parthood relation. Part and part_of are now truly transitive.
* Redesigned imports between modules.
	* Introduced a more layered-approach: importing modules add restrictions relevant to the domain they cover to the imported classes. Not the other way around. In previous versions, the Action module imported the Role and Expression modules (and vice versa), and contained restrictions on its classes expressed using the vocabulary of the Role and Expression modules. In this version these restrictions are moved to the modules that add the vocabulary. I.e. if the Role module 'has something to add' to the definition of a class from the Action module, the restriction is defined in the Role module. This strategy improves the diagnosis of inconsistencies etc.
	* Process module no longer imports Action, Role and Mereology modules
	* Removed Spacetime module
	* Process module now directly imports Place and Time modules
	* Place module no longer directly imports Top
	* Top module no longer imports Mereology, Place and Time modules
	* Action module no longer imports Role and Expression modules

* Reduced the number of GCI (General Concept Inclusion) axioms and inverse properties to speed-up reasoner performance.
	* Rule was inconsistent: both played_by Atom and Composition.
	* Relaxed the definition of Act_of_Law, Assignment, Decision, Delegation and Mandate.
	* Relaxed the definition of Transaction
	* Asserted disjoint relation between Document and Custom
	* Asserted disjoint relation between Role and Action, Role and Agent.
	* Restructured definition of Actor (removed redundant disjoints)
	* Asserted range for observes property: (Belief and (plays some Observation))
	* Relaxed definition of Temporal_Occurrence
	* Added namespace prefix for mereology module to time module
	* Relaxed definition of Relative_Place
	* Relaxed definition of Part, Whole, Atom and Composition. 
	* Corrected range/domain of observer/observes properties
	* Relaxed definition of Propositional_Attitude
	* Relaxed definition of Document
	* Strengthened definition of Qualified
	* Strengthened definition of Mental_Object 
		(added held_by some Agent to equivalentClass restriction)
	* Relaxed definition of Proposition
	* Relaxed definition of Evaluative_Proposition 
		(moved evaluatively_comparable some Evaluative_Proposition to subClassOf restriction)
	* Relaxed definition of Expression 
		(moved medium some Medium to subClassOf restriction)
	* Relaxed definition of Communicated_Attitude 
		(moved (utterer some action:Agent) and (addressee some action:Agent) to subClassOf restriction)
	* Relaxed definition of Artifact
	* Relaxed definition of Epistemic_Role, Function, Social_Role
	* Relaxed definition of Role (someValuesFrom -> min cardinality)
	* Relaxed definition of Organisation_Role
	* Relaxed definition of Qualification/Qualified, added evaluatively_comparable some/all Qualified statements to subClassOf restriction of Qualified.
	* Relaxed the definition of many Epistemic Roles
	* Relaxed the definition of Code, Contract, Regulation and Statute
* Fixed inconsistent class definitions
	* Action disjointWith Plan caused inconsistencies with Continuation, Termination and Initiation. Moved these to the Process module (subclasses of Change)
	* Fixed inconsistency in rule module (Valid_Rule)
	


### Version 1.0.1 - 20070223 - Bugfix Release

* Moved base namespace to http://www.estrellaproject.org/LKIF Core/[module-name].owl 
* Modules are now directly available online. This facilitates loading of files in various editors/viewers.
* Fixed a number of bugs causing the ontology to become OWL-Full (Reported by the OWL Validator at http://phoebus.cs.man.ac.uk:9999/OWL/Validator):
	* Structure Sharing of: http://www.estrellaproject.org/LKIF Core/expression.owl#genid-A17	
	  FIX: Fresh save of file...
	* http://www.estrellaproject.org/LKIF Core/time-modification.owl#initial_date_of rdfs:subPropertyOf http://www.estrellaproject.org/LKIF Core/time.owl#starts. Only allowed between two DatatypeProperties or ObjectProperties.
	  FIX: Renamed http://www.estrellaproject.org/LKIF Core/time.owl#start to  http://www.estrellaproject.org/LKIF Core/time.owl#starts
	* http://www.estrellaproject.org/LKIF Core/time-modification.owl#final_date_of rdfs:subPropertyOf http://www.estrellaproject.org/LKIF Core/time.owl#finishes. Only allowed between two DatatypeProperties or ObjectProperties.
	  FIX: Renamed http://www.estrellaproject.org/LKIF Core/time.owl#finish to  http://www.estrellaproject.org/LKIF Core/time.owl#finishes
	* Untyped Object Property: http://www.estrellaproject.org/LKIF Core/action.owl#permits
	  FIX: Removed stray description of Power
	* Untyped Data Property: http://www.w3.org/2002/07/owl#comment
	  FIX: Removed redefinition of rdfs:comment 
	* Untyped Class: http://www.estrellaproject.org/LKIF Core/action.owl#Power
	  FIX: Removed stray class definition
	* Untyped Individual: http://www.estrellaproject.org/LKIF Core/role.owl#Function
	  FIX: Moved description/comment of Function class from expression.owl to role.owl 
	* Untyped Individual: http://www.estrellaproject.org/LKIF Core/lkif-rules.owl
	  FIX: Removed 
	* http://www.w3.org/2002/07/owl#comment in OWL Namespace (2x)
	  FIX: lkif-rules.owl contained owl:comment elements, changed to rdfs:comment



### Version 1.0   - 20070202 - Initial Release
