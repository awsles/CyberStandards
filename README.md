# CyberStandards
Cyber Security Policies, Standards, Guidelines, Procedures and more - Useful resources for IT and CyberSecurity professionals,
provided under the [Creative Commons Zero license](https://en.wikipedia.org/wiki/Creative_Commons_license#Zero_/_public_domain). 

Many of the requirements and recommendations herein are derived from security patterns and best practices.
In some cases, citations may be included to reference applicable control(s) which can help achieve the desired requirement or recommendation.

# Motivation
As an Information Security professional, I have come across numerous Cyber Security policies, standards, guidelines, and procedures...
not only those of my employers, but also from vendors imposing their own requirements in order to do business with them.
While the spirit of having and following standards is great, many are poorly written, out of date, and/or are simply unachievable.
One large American bank (who shall remain nameless) imposes a 286+ page (!), 10 point type security requirements on their suppliers.
It is so pedandtic that you can barely get through reading it, let alone implementing it fully.

It seems that almost every role I've had in my career has involved some degree of updating information security standards.
often consisting of virtually the same requirements and recommendations that any company would reasonably have.
Each time, I regurgite the obvious requirements from memory, and adjusting these and others as needed for the company's risk appetite.
Furthermore, the statements also become clearer, more sussinct, and often more measurable as I rewrite.

I have never understood why general IT and cybersecurity standards are kept "secret" -- sometimes even WITHIN organizations.
That always makes me laugh because how do you expect folks to adhere to standards they aren't allowed to see? :grin:

# Free, Open Standards
Wouldn't it be great if there were some policy and standards statements open for use?  No one really likes to write these.
It's handy to have a nice starting point.  So this resource is provided for all to use. The examples provided herein are NOT
meant to be exhaustive. But what is provided here can often be used as-is, and fine-tuned for your own environmental requirements.
The requirement and recommendation statements provided herein would complement requirements which may be very specific
(and potentially confidential) to your organization.

# Principles, Policies, Standards, Guidelines, and Procedures
This is the first aspect that usually goes wrong, especially as the terms "policy" and "standard" are often and incorrectly used interchangably.
Every document in the framework should contain boilerplate text which clearly defines the policy framework. For example:

The COMPANY Policy Framework consists of a series of documents which describes goals, objectives, requirements, recommendations, and procedures for various subject areas. This constists of principles, policies, standards, guidelines, and procedures. It is important to understand the distinction and purpose of each within the framework.

* *Values* are prescribed and adopted by the company board of directors and form the foundation by which the company works.
* A *Principle* is a fundamental basis of a system of thought or belief about the way to behave..
* A *Policy* is a formal, brief, high-level statement that typically includes statements to require compliance with associated standards and regulatory requirements with a focus on the desired results and not the means of implementation.
* A *Standard* contains the mandatory and recommended actions and rules to support and conform to a given policy.
* A *Guideline* provides general statements, recommendations, and administrative instructions designed to achieve the policy's objectives by providing a framework within which to implement procedures.
* A *Procedure* describes a process and desired outcome: who does what, when they do it, and under what criteria. A procedure may contain multiple ways to achieve the objective and may or may not be mandatory, depending on what is stated in the associated standards document.

Corporate values drives principles, from which the specific policies are derived. Policies, in turn, drive standards, guidelines, and procedures. Values are usually accompanied by a mission statement to clearly articulate a company's priority and focus.

# MUST and SHOULD
Many standards fail to CLEARLY differentiate what is required vs. what is recommended.
Fortunately, IETF [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt) helps us succinctly resolve this ambiguity.

The first standard in your repertiore should specify how you manage and use principles, policies, standards, guidelines, and procedures.
Importantly, it MUST be clear on key terms to prevent any ambiguity. A statement at the beginning of each document can alay this:

**The following terms have been adapted from IETF RFC 2119 and are used throughout this document to indicate whether a statement is mandatory, recommended or optional: "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL".  These terms are generally capitalized for emphasis within this document.**

Some argue that a standards document should only specify requirements and that guidelines should be used for recommendations.
Personally, I like to keep the related requirements and recommendations together within the same document.
They are more likely to be read this way, and it's one less document to separately track and maintain. 
Furthermore, I prefer to capture key recommendations which themselves may soon become requirements, but haven't yet.
A great example is the use of TLS, combined into a single statement:

* *HTTPS communications MUST use TLS 1.1 or later. However, TLS 1.2 or later SHOULD be used.*

I have also seen cases where security _controls_ such as those found in NIST SP800-53 are used as-is for company standards,
even though security controls are the means by which standard requirements are *achieved* -- the controls themselves are NOT standards.

# Audits
We all cringe a bit around audit time...  Are we really following our own prescribed standards?  Can we evidence that for the auditor?
Many IT and cybersecurity audits measure against YOUR OWN company standards and the specific requirements therein.
That said, many of the best practices and public standards prescribe cetain requirements, which, if your are being measured against that best practice,
you should ensure thag your company's standards adequately cover those requirements. 

### Use '*SHOULD*' but sparingly
The secret here is that you can build in a little bit of *reasonable* wiggle room into your standards.
Sparingly, you can use 'SHOULD' to capture intended objectives without making them a requirement.
Being non-compiant with a 'SHOULD' statement won't be flagged as an audit failure -- unless you are also being measured
againts a prescriptive standard where you MUST have certain requirements in place (i.e., which you cannot skirt by using 'SHOULD' where a 'MUST' is needed).

Don't use this as a crutch... but you can use 'SHOULD' as an interim where you have known gaps inyour controls -- and where you
also have a plan to remediate those gaps and/or a compensating control.

### Use '*where feasible*'
In some cases, a requirement may not be achievable everywhere.
For example, you may wish to require that "*All passwords MUST be at least 10 characters, consisting of a mixture of at least one of each of upper case letters, lower case letters, numbers, and symbols.*".
Sounds great, right?  Ahhh, well SAP only requires 8 characters - and you cannot change this.
So, technically, you will fail your audit point as non-compliant.

A better approach is to reword the requirement to include "*where feasible*".
So your password requirement might become several statements:

* *All systems must require passwords of at least 8 characters. Where feasible, systems MUST require at least 10 characters.*
* *Where feasible, all systems MUST require password complexity, consisting of a mixture of three or more of the following: uppercase letters, lowercase letters, numbers, and symbols.*

See how the above has skirted the issue of imposing a specific password size across all systems -- and therefore risking a potential non-compliance from a rigourous auditor?
We can specify 8 characters as the MUST because we know all our systems support that... but we WANT to require at least 10 on those systems which support it.
Going a step further, you can require users to use 10 or more characters as part of the Employee Use of Company Systems.

### Incorporate Thresholds
Another useful tactic when writing IT and CyberSecurity standards is to incorporate a threshold, at which
you can mark youself as a PASS for audit purposes. Imagine if you had a standard which stated "*Service X MUST be available at all times.*".
One incident, even for a second, would cause you to fail that standard. Of course, no one would really write such a statement
(well, not often anyway 😄).  Instead, a better statement would be something like "*Service X MUST have an availability of 99.999% or better".

Not all requirements lend themselves to thresholds.
For example, one would not reasonly require their web servers to use TLS 1.1 or later 99% of the time.
And an auditor is likely to look dimly on cases where a threshold has been hammered in.

But your standard may define thresholds for measuring non-compliance of the standard, but this should be backed by the impact to the firm's risk profile.
There is no guarantee though that an independent auditor will honor such statements, but they can be a useful tool for your own compliance self assessments.

# Contributing
Content and editorial contributions are welcomed! Please don't share anything confidential.
Edit out any specific resource references (like company, server, or supplier names) and thresholds.
You MAY includes references to specific public cloud providers where a statement pertains to a specific cloud service.

