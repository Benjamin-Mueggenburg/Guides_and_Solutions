## Windows
### - Tensorflow Object Detection API - print location of bounding boxes
**The Problem** <br>
Using 'object_detection_tutorial.ipynb' it outputs and image with a bounding box around the objects it detects. How do you get the x and y cordinates of the bounding boxes? 

**The Solution** <br>
##### Latest version of the code
Following this link [https://stackoverflow.com/a/48172302/8625593](https://stackoverflow.com/a/48172302/8625593) .

Inside of the jupyter notebook. Beneath the line: 
```
vis_util.visualize_boxes_and_labels_on_image_array(
      image_np,
      output_dict['detection_boxes'],
      output_dict['detection_classes'],
      output_dict['detection_scores'],
      category_index,
      instance_masks=output_dict.get('detection_masks'),
      use_normalized_coordinates=True,
      line_thickness=8)
```
You can put this line: `print(output_dict['detection_boxes'])` which will print out boundaries of the boxes. This is all of the predictions as there has been no threshold added. `output_dict['dection_boxes']` is an array, which contains smaller individual arrays each representing a box. The smaller arrays will always have 4 values, ymin, xmin, ymax, xmax
