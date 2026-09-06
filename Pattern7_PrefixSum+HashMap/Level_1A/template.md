HashMap<Integer, Integer> map = new HashMap<>();

map.put(0, 1);

int prefix = 0;

for (int num : nums) {

    prefix += num;

    // check something using prefix

    map.put(prefix, map.getOrDefault(prefix, 0) + 1);
}