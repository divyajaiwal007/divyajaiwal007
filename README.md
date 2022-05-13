
## Usage of the face mask perceptor input callback
## The face mask perceptor takes multiple inputs
## Each input is a sub section of the frame containing only the face
## Each face is retrieved using the people perceptor POM7
## Additional transformations (like color conversion) can be done here

__people_perceptor_name = 'people'

def__face_mask_input_callback (input_data, pom, config):
data = []
people = pom. get_perceptor (__people_perceptor_name) people()
for person_id in people:
    person = people person_id]
    if not person["has_face"]:
       continue
       
face pom.get_perceptor (__people_perceptor_name). faceImage (person_id)
rgb_face = cv2.cvtColor (face, cv2.COLOR_BGR2RGB)
data append({"input": rgb_face, "person_id": person_id})
