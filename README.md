# Causal inference

## Frameworks and surveys

- **[Causal inference in statistics](https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf)** — 2009. Connects structural models, interventions, counterfactuals, and potential outcomes; emphasizes that causal conclusions depend on assumptions beyond observed associations.
- **[Introduction to causal inference](https://pmc.ncbi.nlm.nih.gov/articles/PMC2836213/)** — 2010. Separates defining a causal question, stating assumptions, identifying an estimand, and estimating it; covers interventions, counterfactuals, and mediation.
- **[Causality and statistical learning](https://www.stat.columbia.edu/~gelman/research/published/causalreview4.pdf)** — 2011. Gelman's review distinguishes estimating effects of specified interventions from explaining observed outcomes, comparing graphical and potential-outcome approaches.
- **[Causal discovery and inference survey](https://link.springer.com/article/10.1186/s40535-016-0018-x)** — 2016. Reviews conditional-independence and structural-equation approaches, their identifiability assumptions, and extensions from independent observations to time series.
- **[Learning causality with data](https://arxiv.org/abs/1809.09337)** — 2018. Surveys treatment-effect estimation and causal-relation discovery, examining where larger datasets help and where identification still requires substantive assumptions.
- **[Statistical Tools for Causal Inference](https://chabefer.github.io/STCI/)** — Sylvain Chabé-Ferret's open text covers causal estimands, identification, estimators, uncertainty, and research design. The linked edition is dated 2025.
- **[Bayesian causal inference](https://arxiv.org/abs/2206.15460)** — 2022. Reviews potential-outcome estimands, priors, identification, overlap, and sensitivity analysis; also considers instrumental variables and time-varying treatments.

## Potential outcomes and identification

- **[Neyman's field experiments](https://doi.org/10.1214/ss/1177012031)** — 1990. English translation of the 1923 work: represents potential yields by crop variety and plot and derives randomization-based uncertainty, although only one potential yield per plot is observed.
- **[Rubin's treatment-effect paper](https://www.ets.org/research/policy_research_reports/publications/article/1974/hrbx.html)** — 1974. Historical reference on estimating causal effects in randomized and nonrandomized studies; the linked institutional record identifies the original Journal of Educational Psychology article.
- **[Potential outcomes: design and modeling](https://www.tandfonline.com/doi/abs/10.1198/016214504000001880)** — 2005. Defines effects through comparisons of potential outcomes and models treatment assignment separately; connects experimental design, Bayesian modeling, and decisions based on causal estimates.
- **[Propensity scores](https://academic.oup.com/biomet/article-abstract/70/1/41/240879)** — 1983. The treatment probability given observed covariates is a balancing score. Causal adjustment requires strongly ignorable assignment, including overlap; balancing observed covariates does not remove hidden confounding.
- **[Back-door adjustment](https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf)** — 2009. Selects covariates that block back-door paths without including descendants of treatment. The criterion depends on a causal graph; adding more adjustment variables is not automatically helpful.
- **[Identification beyond adjustment](https://arxiv.org/abs/1206.6876)** — 2006. Shpitser and Pearl give a complete algorithm for identifying conditional intervention distributions from a causal graph and observational law. Some effects need more than adjustment; the algorithm assumes the graph, not its discovery.
- **[Instrumental variables](https://dash.harvard.edu/entities/publication/73120378-82c1-6bd4-e053-0100007fdf3b)** — 1996. Under the paper's identification assumptions, the instrumental-variable estimand identifies an average effect for compliers. Without those assumptions, the ratio lacks that causal interpretation.
- **[Proximal causal learning](https://arxiv.org/abs/2009.10982)** — 2020. Identifies effects using proxies for hidden confounders under proxy-independence, confounding-bridge and completeness conditions; sufficiently informative proxies replace full confounder measurement.

## Treatment-effect estimation with machine learning

- **[Causal trees](https://arxiv.org/abs/1504.01132)** — 2015. Partitions covariate space by treatment-effect heterogeneity. Honest estimation uses separate samples to choose partitions and estimate leaf effects, under randomized assignment or unconfoundedness.
- **[Causal forests](https://arxiv.org/abs/1510.04342)** — 2015. Extends random forests to heterogeneous treatment effects with honest trees; consistency and uncertainty results require unconfoundedness and the paper's regularity assumptions.
- **[Generalized random forests](https://arxiv.org/abs/1610.01271)** — 2016. Learns adaptive neighborhood weights for local moment equations, supporting heterogeneous treatment effects, instrumental-variable effects, and other targets beyond ordinary outcome prediction.
- **[Double/debiased machine learning](https://arxiv.org/abs/1608.00060)** — 2016. Combines orthogonal scores with cross-fitting to reduce sensitivity to nuisance-model errors. Valid causal interpretation still requires identification assumptions; predictive accuracy alone is insufficient.
- **[Approximate residual balancing](https://arxiv.org/abs/1604.07125)** — 2016. Combines balancing weights and regularized outcome regression for average treatment effects in high-dimensional linear models, with overlap and unconfoundedness assumptions.
- **[Meta-learners and the X-learner](https://arxiv.org/abs/1706.03461)** — 2017. Wraps supervised learners to estimate conditional average treatment effects. The X-learner exploits structure and unequal treatment-group sizes; no compared learner is uniformly best.
- **[R-learner](https://arxiv.org/abs/1712.04912)** — 2017. First estimates outcome and treatment nuisance functions, then optimizes a residualized treatment-effect objective; its quasi-oracle result is proved for a specified penalized-kernel setting.
- **[Doubly robust CATE estimation](https://arxiv.org/abs/2004.14497)** — 2020. Analyzes two-stage treatment-effect estimators and local polynomial double-residual regression; gives error bounds and conditions for oracle efficiency rather than assuming flexible learners guarantee it.

## Policy evaluation and mechanisms

- **[Difference-in-differences with staggered timing](https://arxiv.org/abs/1803.09015)** — 2018. Identifies group/time effects under conditional parallel trends and supports explicit aggregation across treatment cohorts, avoiding a single effect summary that hides timing heterogeneity.
- **[Synthetic controls](https://www.mit.edu/~jhainm/Paper/ccs.pdf)** — 2010. Constructs a weighted comparison from untreated units to match a treated unit before intervention; comparative-case inference depends on a credible donor pool and pre-intervention fit.
- **[Causal mediation](https://imai.fas.harvard.edu/research/files/BaronKenny.pdf)** — 2010. Separates definition, identification, estimation, and sensitivity analysis for mediation effects, accommodating nonlinear models and making identifying assumptions explicit.
- **[Sensitivity to omitted confounding](https://escholarship.org/uc/item/0pg6471b)** — 2020. Extends omitted-variable-bias analysis for regression. The robustness value quantifies how strongly unobserved confounding would need to relate to treatment and outcome to change a conclusion.

## Graph discovery from independent observations

- **[PC algorithm](https://jmlr.org/papers/v8/kalisch07a.html)** — 2007. Uses conditional-independence information to estimate a graph skeleton and equivalence class. High-dimensional consistency is established for sparse Gaussian DAGs under stated assumptions.
- **[Copula PC](https://www.cs.ru.nl/~perry/publications/2016/ECML2016/CuiECML16.pdf)** — 2016. Extends PC to mixed continuous/discrete data under a Gaussian-copula model, estimating correlations through rank-based Gibbs sampling before graph discovery.
- **[FCI and latent variables](https://arxiv.org/abs/1302.4983)** — 1995. Studies causal conclusions from conditional independences when latent variables and selection bias may exist; identifies features supported by the assumptions rather than promising a unique complete causal graph.
- **[Greedy equivalence search](https://jmlr.org/papers/v3/chickering02b.html)** — 2002. Searches over DAG equivalence classes with locally scored operators. Large-sample recovery guarantees depend on distributional and scoring conditions, not merely finding a high-scoring graph.
- **[LiNGAM](https://jmlr.org/papers/v7/shimizu06a.html)** — 2006. Uses independent component analysis to identify linear acyclic causal structure under non-Gaussian disturbances and no hidden confounders.
- **[Partially Gaussian linear models](https://arxiv.org/abs/1206.3260)** — 2008. Combines conditional-independence and independent-component approaches, characterizing which linear acyclic structures remain distinguishable when some disturbances are Gaussian.
- **[Nonlinear additive-noise models](https://proceedings.neurips.cc/paper/2008/hash/f7664060cc52bc6f3d620bcedc94a4b6-Abstract.html)** — 2008. Uses restrictions from additive independent noise to infer causal direction in nonlinear systems; identifiability depends on the functional and noise assumptions.
- **[NOTEARS](https://arxiv.org/abs/1803.01422)** — 2018. Expresses DAG acyclicity as a smooth equality constraint for continuous structure optimization. An acyclic fitted graph alone does not establish that its arrows are causal.

## Discovery across environments

- **[Invariant causal prediction](https://arxiv.org/abs/1501.01332)** — 2015. Tests which predictor sets retain an invariant conditional distribution for a target across environments. Causal-parent confidence statements require the paper's structural and intervention assumptions.
- **[Transportability](https://arxiv.org/abs/1312.7485)** — 2013/2014. Uses graphical assumptions about population differences to combine source experiments with target observations. Bareinboim and Pearl decide when a causal effect can transfer; predictive domain adaptation need not identify that effect.

## Time series and temporal discovery

- **[Granger's original formulation](https://doi.org/10.2307/1912791)** — 1969. Defines causality through improved prediction from past information. Apparent instantaneous effects can reflect coarse sampling or omitted variables; the result depends on the available information set.
- **[Extended Granger causality](https://www.dcs.warwick.ac.uk/~feng/papers/Analyzing%20multiple%20nonlinear%20time%20series.pdf)** — 2004. Extends Granger's predictive-dependence approach to nonlinear multivariate time series and evaluates it on chaotic systems; inferred direction remains tied to the observed variables and model.
- **[Additive nonlinear time-series models](https://jmlr.org/papers/v9/chu08a.html)** — 2008. Combines conditional-independence tests from additive regressions with temporal ordering to recover causal information for a specified class of stationary nonlinear systems.
- **[Large-scale nonlinear Granger causality](https://arxiv.org/abs/2009.04681)** — 2020. Uses nonlinear state-space transformations to estimate multivariate directed predictive interactions from short, high-dimensional series; evaluates simulated networks and fMRI recordings.
- **[PCMCI+](https://proceedings.mlr.press/v124/runge20a.html)** — 2020. Selects conditioning sets for lagged and contemporaneous discovery in autocorrelated time series; assumes causal sufficiency, so latent-confounder settings require a different method.

## Causal representations

- **[Causal representation learning](https://arxiv.org/abs/2102.11107)** — 2021. Frames discovery of causal variables from low-level observations as a distinct problem from learning a graph over given variables, linking causal assumptions to transfer and generalization.

## Software

- **[Tigramite](https://jakobrunge.github.io/tigramite/)** — Time-series causal discovery and effect estimation with linear and nonparametric conditional-independence tests; includes distinct methods for different temporal and confounding assumptions.
- **[DoWhy](https://www.pywhy.org/dowhy/v0.13/)** — Separates causal modeling, identification, and estimation, with sensitivity and refutation tools; also supports structural causal models, interventions, and counterfactual queries.
- **[EconML](https://www.pywhy.org/EconML/)** — Implements heterogeneous-effect estimators, including double machine learning, forests, meta-learners, and instrumental-variable methods, with inference and validation interfaces.

## Related Topics

- [Bayesian Networks](https://mlpapers.org/bayesian-nets/)
- [Bayesian Inference](https://mlpapers.org/bayesian-inference/)
- [Models](https://mlpapers.org/models/)
