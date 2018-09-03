<!DOCTYPE html>
<html>
<head>
<style>
div {
    margin: 70px;
    border: 1px solid #4CAF50;
}
</style>
</head>
<body>

<h1>Data</h1>

<div>
  <a href="experiments/experiments.html">
    <h3> Experiment Results </h3>
  </a>
</div>

<div>
    <a href="experiment_0/experiment_0.html">Experiment 0</a>
    <ul>
      <li>Training: F1(0) -> F1(9)</li>
      <li>Testing: F1(0) -> F1(9), ... F6(0) ->  F6(9) - RANDOM</li>
      <li>number of random xs: 100</li>
      <li>number of Hf: 100</li>
      <li>number of functions: 10</li>
      <li>final shape: (100000, 22)</li>
      <li>shuffled</li>
      <li>batch_size: 128</li>
      <li>epochs: 20</li>
    </ul> 
</div>

<div>
    <a href="experiment_1/experiment_1.html">Experiment 1</a>
    <ul>
      <li>Training: F1(0) -> F1(9), F5(0) -> F5(9)</li>
      <li>Testing: F1(0) -> F1(9), ... F6(0) ->  F6(9) - RANDOM</li>
      <li>number of random xs: 100</li>
      <li>number of Hf: 100</li>
      <li>number of functions: 20</li>
      <li>final shape: (200000, 22)</li>
      <li>shuffled</li>
      <li>batch_size: 128</li>
      <li>epochs: 20</li>
    </ul> 
</div>

<div>
    <a href="experiment_2/experiment_2.html">Experiment 2</a>
    <ul>
      <li>Training: F1(0) -> F1(9), F5(0) -> F5(9), F3(0) -> F3(9)</li>
      <li>Testing: F1(0) -> F1(9), ... F6(0) ->  F6(9) - RANDOM</li>
      <li>number of random xs: 100</li>
      <li>number of Hf: 100</li>
      <li>number of functions: 30</li>
      <li>final shape: (300000, 22)</li>
      <li>shuffled</li>
      <li>batch_size: 128</li>
      <li>epochs: 50</li>
    </ul> 
</div>

<div>
    <a href="experiment_3/experiment_3.html">Experiment 3</a>
    <ul>
      <li>Training: F1(0) -> F1(50), F5(0) -> F5(50), F3(0) -> F3(50)</li>
      <li>Testing: F1(0) -> F1(9), ... F6(0) ->  F6(9) - RANDOM</li>
      <li>number of random xs: 100</li>
      <li>number of Hf: 100</li>
      <li>number of functions: 153</li>
      <li>final shape: (1530000, 22)</li>
      <li>shuffled</li>
      <li>batch_size: 128</li>
      <li>epochs: 50</li>
    </ul> 
</div>

<div>
    <a href="experiment_4/experiment_4.html">Experiment 4</a>
    <ul>
      <li>Training: F1(0) -> F1(9), F5(0) -> F5(9), F6(0) -> F6(9)</li>
      <li>Testing: F1(0) -> F1(9), ... F6(0) ->  F6(9) - RANDOM</li>
      <li>number of random xs: 100</li>
      <li>number of Hf: 100</li>
      <li>number of functions: 30</li>
      <li>final shape: (300000, 22)</li>
      <li>shuffled</li>
      <li>batch_size: 128</li>
      <li>epochs: 20</li>
    </ul> 
</div>

</body>
</html>

