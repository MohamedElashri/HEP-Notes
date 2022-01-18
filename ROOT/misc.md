## TTree::Draw() notes

TTree::Draw() is a quick way to produce plots from root files. 
An example TTree::Draw() script:

```cpp
void ttreeDrawExample() {
  TTree *t = (TTree*)_file0->Get("analysistree/anatree");
  
  TH1F *h = new TH1F("h", "", 50, 0, 50);

  t->Draw("tBranchName >> h", "some_cut");

  h->Draw();
}
```

## Turn off messages

To turn off messages like:

```
Info in <TCanvas::Print>: png file my_plot.png has been created
```

add in:

```cpp
gErrorIgnoreLevel = kWarning
```

or for PyROOT (assuming you have `import ROOT`):

```py
ROOT.gErrorIgnoreLevel = ROOT.kWarning
```

