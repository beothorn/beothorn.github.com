Do whenever possible, no hard rules.

Code structure follow user interface (menu structure?)

Organize by business logic not by layer

Domain>service
Domain>resource

instead of

service>All Services for all domains
resource>All resources for all domains

because a bug happens on a domain, not on a layer

code must be travesable (avoid magic, macros, annotations, stuff that cant be followed)

use the same terms as the user interface

make logs unique and searchable

Code dependencies only up or down the directory tree, avoid using non utilitary stuff from sibling folders. Rearrange common used code to bubble up so the higher in the directory tree, the most common/abstract.

Comments with key words, comment why this is being done.