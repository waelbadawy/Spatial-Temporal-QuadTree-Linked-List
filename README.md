# Spatial-Temporal-QuadTree-Linked-List
Spatial Temporal QuadTree Linked List


=

                                *
                              /| |\
                             * * * *

                     Simple quadtrees for c.
            see test.c for usage, and use make to build

And the api goes:

quadtree_point_t*
quadtree_point_new(double x, double y);

void
quadtree_point_free(quadtree_point_t *point);


quadtree_bounds_t*
quadtree_bounds_new();

void
quadtree_bounds_extend(quadtree_bounds_t *bounds, double x, double y);

void
quadtree_bounds_free(quadtree_bounds_t *bounds);


quadtree_node_t*
quadtree_node_new();

void
quadtree_node_free(quadtree_node_t *node, void (*value_free)(void*));

int
quadtree_node_ispointer(quadtree_node_t *node);

int
quadtree_node_isempty(quadtree_node_t *node);

int
quadtree_node_isleaf(quadtree_node_t *node);

void
quadtree_node_reset(quadtree_node_t* node, void (*key_free)(void*));

quadtree_node_t*
quadtree_node_with_bounds(double minx, double miny, double maxx, double maxy);

quadtree_t*
quadtree_new(double minx, double miny, double maxx, double maxy);

void
quadtree_free(quadtree_t *tree);

quadtree_point_t*
quadtree_search(quadtree_t *tree, double x, double y);

int
quadtree_insert(quadtree_t *tree, double x, double y, void *key);

void
quadtree_walk(quadtree_node_t *root,
              void (*descent)(quadtree_node_t *node),
              void (*ascent)(quadtree_node_t *node));


