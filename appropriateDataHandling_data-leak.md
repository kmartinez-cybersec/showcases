<h1>Determining Appropriate Data Handling Practices</h1>
<h2>Description</h2>
A sales manager shared access to a folder of internal-only documents with their team during a meeting. The folder contained files associated with a new product that has not been publicly announced. It also included customer analytics and promotional materials. After the meeting, the manager did not revoke access to the internal folder, but warned the team to wait for approval before sharing the promotional materials with others.
<br />
<br />
During a video call with a business partner, a member of the sales team forgot the warning from their manager. The sales representative intended to share a link to the promotional materials so that the business partner could circulate the materials to their customers. However, the sales representative accidentally shared a link to the internal folder instead. Later, the business partner posted the link on their company's social media page assuming that it was the promotional materials.

<h2>Response</h2>

| Control | Least Privilege |
| --- | --- |
| Issues | Access was not limited to the sales team and their manager; the business partner should not have permissions to share the promotional material to social media. |
| Regulations | [NIST SP 800-53: AC-6](https://csf.tools/reference/nist-sp-800-53/r5/ac/ac-6/) addresses how organizations can improve their security posture via implementation of least privilege, along with recommendations for how to best implement the principle of least privilege. |
| Recommendations | Restrict access to resources based on the roles of users; Conduct regular audits of user privileges. |
| Reasoning | Data leaks such as the one that occurred can be prevented if link sharing to sensitive materials is restricted to employees only; Requiring regular access audits for permissions user and file permissions would help to catch misconfigurations of permissions before a data leak occurs. |

