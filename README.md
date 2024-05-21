# Approaches

Since there are potentially multiple persons on the scene, we will detect persons first, and select and focus the extended largest person area. If possible, we should set up the camera to minimize the possibility of multiple persons on the scene.

Algorithm 1: Motion Detection Based

```
1. detect persons
2. select the largest person's bounding box
3. expand the bounding box by a scale (e.g. 2)
4. while (true):
    5. detect motion
    6. detect whether the motion area crosses the boundary
    7. if boundary crossed:
        8. increase repetition count
```

Algorithm 2: Key Points Detection Based

```
1. detect persons
2. select the largest person's bounding box
3. expand the bounding box by a scale (e.g. 2)
4. while (true):
    5. detect body key points (i.e. estimate pose)
    6. detect whether a key point crosses the boundary
    7. if boundary crossed:
        8. increase repetition count
```

Algorithm 3: RepNet Based

```
1. detect persons
2. select the largest person's bounding box
3. expand the bounding box by a scale (e.g. 2)
4. while (true):
    5. run [repnet model](https://sites.google.com/view/repnet)
    6. if repetition detected:
        7. increase repetition count
```

Algorithm 4: Ensemble Algorithm 1, 2 and 3
