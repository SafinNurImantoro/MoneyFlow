# Receipt Storage

Bucket: private.

Recommended object path:

users/{user_id}/transactions/{transaction_id}/{uuid}.{ext}

Rules:
- user can upload only into own prefix
- user can read only own transaction receipts
- allowed MIME: image/jpeg, image/png, image/webp
- enforce file size limit
- validate file type client and server side
- use signed access for viewing private objects
- do not expose service key
- do not treat storage metadata tables as application-owned tables

Receipt metadata lives in `receipts`.
