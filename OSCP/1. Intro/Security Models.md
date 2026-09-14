
A [_security model_](https://en.wikipedia.org/wiki/Computer_security_model) is a type of schema that is used to implement security controls in information systems. They rarely specify specific controls, but they present a theoretical framework and, in some cases, a set of rules that can be implemented in several different contexts.

Many of the most well-known models target access controls. We'll focus on examples of these in this section. Some of these specifically focus on confidentiality or integrity, others are more general.


	These Models below Focus on Confidentiality
# Bell–LaPadula model
First, let's consider a security model that deals primarily with _confidentiality_. The [_Bell–LaPadula model_](https://en.wikipedia.org/wiki/Bell%E2%80%93LaPadula_model) is used to enforce access controls in systems with multiple security levels (for instance, unclassified, confidential, secret and top secret). It's often used in a government or military context to determine who can access what objects at the various security levels. In this model, individuals cannot read content with a security level higher than their own (known as the _Simple Security Property_) or write content with a security level lower than their own (known as the _Star Security Property_). In certain contexts, they may not be allowed to read or write at a level other than their own (known as the _Discretionary Security Property_).

# Brewer and Nash Model
Similarly, the [_Brewer and Nash model_](https://en.wikipedia.org/wiki/Brewer_and_Nash_model) is used to enforce access controls to maintain confidentiality, but with the specific aim of minimizing conflict of interest. This may be used by accounting or consulting organizations. The model uses data segregation and dynamic access controls. Dynamic access controls may function by denying access to certain individuals based on other information that they have viewed or have access to. For instance, an organization that works with customers who compete with one another may temporarily restrict an individual from accessing a company's data once they have accessed data belonging to their competitor.


	These Models below Focus on Integrity
# Biba Model
Next, let's consider some security models that deal primarily with _integrity_. The [_Biba model_](https://en.wikipedia.org/wiki/Biba_Model) is also used to enforce access controls and is designed to protect the _integrity_ of information where individuals and information are assigned different integrity levels. In this model, individuals cannot read data with a lower integrity level than their own (known as the _Simple Integrity Property_) or write content with an integrity level higher than their own (known as the _Star Integrity Property_). Another rule, states that individuals cannot request access to information with a higher integrity level than their own (known as the _Invocation Property_).

# Clark Wilson Model
The [_Clark-Wilson model_](https://en.wikipedia.org/wiki/Clark%E2%80%93Wilson_model) is another module used to protect data integrity. This is implemented through _access control triples_ (or simply _triples_), which consist of a _subject_, _program_ (also known as a _transaction_) and _object_. According to this model, individual subjects don't have direct access to data objects but only access and modify them through a series of _programs_, which themselves operate on data objects and enforce integrity policies.


	These are general Security Models
# Role-Based Access Control (RBAC)
Other access control security modules are focused on access controls more generally. One example of this is [_Role-Based Access Control_](https://csrc.nist.gov/glossary/term/role_based_access_control) (RBAC). This security model, widely used in cloud computing Identity and Access Management (IAM), grants permissions to roles, which are in turn applied to individual users. Rather than permissions being granted to each user directly, permissions are granted to users based on the roles that they have.

# Attribute-Based Access Control (ABAC)
Another variant is [_Attribute-Based Access Control_](https://csrc.nist.gov/Projects/attribute-based-access-control) (ABAC). This security model is based on a series of attributes that are applied to users and objects, and rules use these attributes to determine which users can perform which types of access on which objects. ABAC has the advantage of providing more granular access control and of being more dynamic.




	This is a model which is used currently!

# Shift-Left Security

One of the best ways to avoid extra costs and impacts on availability is to design an entire system so that security is built into the service architecture, rather than requiring many additional software layers. To design systems with built-in security, the idea of [_shift-left security_](https://devopedia.org/shift-left) can improve efficiency. The idea of shift-left security is to consider security engineering from the outset when designing a product or system, rather than attempt to bake it in after the product has been built.

Without shift-left security, we might have developers shipping products without security, and then need to add additional layers of security on top of, or along with, the product. If the security team is involved in the development process, we have a better chance of creating a product with controls built in, making a more seamless user experience as well as reducing the need for additional security services.



	This technique is used to prevent misuage of Admin rights incase of privelege Escalation
# Administrative Segmentation
It may seem okay to have an administrator bypass security controls based on their role and functional needs. Shouldn't we trust our administrators? However, when a threat is internal or otherwise able to obtain valid administrative credentials, our security posture becomes weaker. To defeat internal threats and threats that have acquired valid credentials or authentication capability, we must segment controls so that no single authority can bypass all controls. To accomplish this, we may need to split controls between application teams and administrators, or split access for administration between multiple administrators, as with [_Shamir's Secret Sharing_](https://en.wikipedia.org/wiki/Shamir%27s_Secret_Sharing) (SSS).

With SSS, we might design a system so that three different administrator authorizations are required to authorize any one administrative root access. Shamir's secret sharing scheme enables a system to split access authorization requirements between multiple systems or persons. With this in place, we can design a system so that no one person has the root credentials.

