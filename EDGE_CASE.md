# Document your edge case here
- To get marks for this section you will need to explain to your tutor:
1) The edge case you identified

mark is optional on POST but doesnt specify what are the valid values. what happens if someone submits a -50 or 999 or saodnanjsd..

this could corrupt stats like avg, min, max!!!

2) How you have accounted for this in your implementation

in both POST /students and PUT /students/{id} or create and update student it contains:

if mark is not None and (not isinstance(mark, int) or mark < 0 or mark > 100):
        return jsonify({"error": "mark must be an integer between 0 and 100"}), 404

so if mark fails the check, API returns 404.
