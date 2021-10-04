## TTree::Draw() notes

TTree::Draw() is a quick way to produce plots from root files. 
An example TTree::Draw() script:

```c++
void ttreeDrawExample() {
  TTree *t = (TTree*)_file0->Get("analysistree/anatree");
  
  TH1F *h = new TH1F("h", "", 50, 0, 50);

  t->Draw("tBranchName >> h", "some_cut");

  h->Draw();
}
```
