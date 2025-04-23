import java.util.*;

class Node {
    int data;
    Node left, right;

    public Node (int value) {
        data = value;
        left = right = null;
    }
}

public class Binarytree {
    Node root;

    public Node insert (Node node, int value) {
        if (node == null) {
            return new Node(value);
        }

        if (value < node.data) {
            node.left = insert(node.left, value);
        }
        else if (value > node.data) {
            node.right = insert(node.right, value);
        }
        else {
            System.out.println("Cant duplicat");
        }
        return node;
    }

    public void inOrder(Node node) { //buat tampilan tapi dari yg terkecil
        if (node != null) {
            inOrder(node.left);
            System.out.print(node.data + " ");
            inOrder(node.right);
        }
    }

    public Node delete (Node node, int key) {
        if (node == null) {
            return null;
        }

        if (key < node.data) {
            node.left = delete (node.left, key);
        }
        else if (key > node.data) {
            node.right = delete (node.right, key);
        }
        else {
            if (node.left == null) {
                return node.right;
            }
            else if (node.right == null) {
                return node.left;
            }

            node.data = minValue (node.right);
            node.right = delete (node.right, node.data);
        }
        return node;
    }

    public int minValue (Node node) {
        int min = node.data;
        while (node.left != null) {
            min = node.left.data;
            node = node.left;
        }
        return min;
    }

    public boolean search (Node node, int key) {
        if (node == null) {
            return false;
        }
        if (key == node.data) {
            return true;
        }
        if (key < node.data) {
            return search(node.left, key);
        }
        else {
            return search(node.right, key);
        }
    }

    public static void main(String[] args) throws Exception {
        Binarytree tree = new Binarytree();

        tree.root = tree.insert(tree.root, 50);
        tree.root = tree.insert(tree.root, 25);
        tree.root = tree.insert(tree.root, 80);
        tree.root = tree.insert(tree.root, 30);
        tree.root = tree.insert(tree.root, 10);
        
        System.out.println(tree.search(tree.root, 25));
        tree.root = tree.delete(tree.root, 10);
        
        tree.inOrder(tree.root);
    }
}

