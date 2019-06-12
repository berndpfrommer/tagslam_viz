# Visualization for TagSLAM

This repository is useful for visualizing data produced by
[TagSLAM](https://github.com/berndpfrommer/tagslam), a package for
fiducial marker based SLAM.

## How to wrap a tag onto a mesh

[Here][docs/README_blender.md] is a cook book recipe on how to texture
a single surface with blender.

## How to generate mesh files

Use the ``convert_tags.bash`` in the src directory to mass convert
apriltags. Modify the script to process different families

## How to visualize tags

This package contains a python script that generates a urdf robot
model that you can visualize in rviz. Use the following launch file as
an example

    roslaunch tagslam_viz visualize_tags.launch

It references the ``example_tag_id.yaml`` file in the ``config``
subdirecory. Such a file is actually produced by tagslam when you run
it. It is called ``body_poses.out`` and can be copied like this:

    cp ~/.ros/body_poses_out.yaml `rospack find  tagslam_vis`/config/example_tag_id.yaml
