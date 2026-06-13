# **From Geospatial Analysis to Spatial Biology: A Shared Logic of Spatial Data Quality.**



# This document explains the methodological foundation of Project 1 — the transfer of spatial data quality assessment principles from geodesy, photogrammetry and metrology into bioimage analysis.

# \---

# **Why compare geospatial analysis and spatial biology?**



# Satellite imagery and biological tissue images are very different types of data. They differ in scale, subject matter, acquisition methods and scientific context.

# However, both disciplines rely on spatial data: objects have coordinates, their relative positions matter, and conclusions depend on spatial relationships between them.

# Both therefore face a similar fundamental question: How reliable are these spatial data?

# \---

# **Similar challenges in spatial data quality assessment**



# The analogy is made at the level of spatial data quality assessment, not at the level of the scientific objects being studied.

# | Geodesy / Remote Sensing | Spatial Biology |

# |--------------------------|-----------------|

# | Object: Earth's surface | Object: tissue section |

# | Pixel: area of Earth's surface | Pixel: area of biological tissue |

# | Coordinate: geographic position | Coordinate: position of a cell in tissue |

# | Error: inaccuracy in object coordinates | Error: inaccuracy in cell position |

# | Scale: metres, kilometres | Scale: micrometres |

# 

# Scale, objects and units differ. The analytical task, however, remains the same:

# Spatial data contain uncertainty Errors must be measured and interpreted Result quality must be evaluated An informed decision about data reliability must be made

# \---

# **A simple example**



# Consider a map with a coordinate error. A routing algorithm may function correctly and still lead the user to the wrong location. The problem is not in the algorithm — it is in the spatial foundation the algorithm operates on. All subsequent calculations are correct, but relative to incorrect coordinates.

# \---

# **Applying the Same Logic to Spatial Biology**



# The same principle applies to biological image registration. If registration contains an error, all subsequent analysis steps operate on a distorted spatial foundation.

# Registration error Distorted cell coordinates Incorrect spatial relationships Incorrect spatial analysis Risk of incorrect biological conclusions

# A biological conclusion may appear convincing while relying on spatial data whose quality has not been adequately confirmed.

# \---

# **Why a single metric is not sufficient**



# A registration result alone does not answer the question of whether the data are suitable for further analysis. Different checks answer different questions:

# Registration result RMSE — how large is the error? Error map — where does the error occur? Nature of errors — why does the error occur? Validation — can the method be trusted? Decision — are the data suitable for further analysis?

# No single metric can answer all of these questions simultaneously. Together, these checks form a chain of independent evidence and support a justified conclusion about data reliability.

# \---

# **Why Project 1 is structured this way**



# The goal of Project 1 was not only to perform image registration. The primary aim was to assess the reliability of the result before biological interpretation.

# For this reason, the project combines quantitative metrics, spatial error analysis, control point validation and extended validation experiments. Each step addresses a separate question and contributes independently to the overall quality assessme



# **Applying Spatial Data Quality Principles**



# Project 1 combines learning the foundations of bioimage analysis with applying a previously developed approach to spatial data quality assessment.

# Training in geodesy and metrology established the following analytical principles:

# Every measurement contains uncertainty Errors must be measured and interpreted A single metric is not sufficient for a decision Results require independent verification Confidence is built on a body of evidence



# **This reasoning determined the structure of Project 1.**





# | Geodesy / Metrology | Project 1 |

# |---------------------|-----------|

# | Control network | Registration control points |

# | Root Mean Square Error (RMSE) | RMSE |

# | Residual errors | Error map |

# | Local and global accuracy | Centre and border zone |

# | Systematic error | Border effect |

# | Calibration against reference | Pipeline validation |

# | Reproducibility | Fixed random seed |

# | Decision on data suitability | Decision |

# 

# The central question of the project is not only what registration result was obtained, but how reliable that result is and what evidence supports that assessment.

