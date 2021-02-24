# GenSchedule

Timetable scheduling using genetic algorithms.

## Steps

1. Fill:
    ```python
    C1 = 1  # uniformity
    C2 = 1  # tightness
    C3 = 1  # suitability
    C4 = 0.1  # sleep
    C5 = 1  # day_grouping
    C6 = 1  # week_grouping
    
    CLASSES_PER_DAY = 4
    WORKING_DAYS = 5
    PLACES = CLASSES_PER_DAY * WORKING_DAYS
    
    SUBJECTS = [
        Subject(name='AG', numbers={SubjectType.LECTURE: 1, SubjectType.SEMINAR: 2}),
        Subject(name='MA', numbers={SubjectType.LECTURE: 2, SubjectType.SEMINAR: 2}),
        Subject(name='PR', numbers={SubjectType.LECTURE: 1, SubjectType.SEMINAR: 1}),
        Subject(name='EN', numbers={SubjectType.LECTURE: 0, SubjectType.SEMINAR: 3}),
        Subject(name='DM', numbers={SubjectType.LECTURE: 1, SubjectType.SEMINAR: 1}),
    ]
    
    SUITABLE_TIME = {
        WeekDay.MON: {1: ['AG'], 2: [], 3: [], 4: []},
        WeekDay.TUE: {1: ['MA'], 2: ['PR'], 3: ['PR'], 4: []},
        WeekDay.WED: {1: ['AG'], 2: ['AG'], 3: ['MA'], 4: []},
        WeekDay.THU: {1: ['DM'], 2: ['EN'], 3: ['MA', 'EN'], 4: []},
        WeekDay.FRI: {1: ['MA'], 2: ['DM'], 3: [], 4: []}
    }
    ```

2. Receive:
    ```
    gen	nevals	avg    	std     	min   	max    
    0  	300   	2.91481	0.291041	1.7581	3.69857
    1  	189   	3.09384	0.208402	2.2381	3.69857
    2  	171   	3.20138	0.212053	2.43392	3.69857
    3  	186   	3.24289	0.225741	2.2781 	3.69857
    4  	179   	3.28457	0.232168	1.93117	3.69857
    5  	187   	3.30843	0.244352	2.46857	3.71857
    6  	179   	3.35342	0.245704	2.32952	3.80623
    ...
    499	187   	4.1657 	0.045359 	3.68714	4.17143
    500	166   	4.15778	0.0618725	3.68714	4.17143
    
    MON:
    1)
    2) MA SEMINAR
    3) MA SEMINAR
    4) DM LECTURE
    
    TUE:
    1)
    2) PR LECTURE
    3) AG SEMINAR
    4) AG SEMINAR
    
    WED:
    1)
    2) AG LECTURE
    3) MA LECTURE
    4) MA LECTURE
    
    THU:
    1)
    2) EN SEMINAR
    3) EN SEMINAR
    4) EN SEMINAR
    
    FRI:
    1)
    2) DM SEMINAR
    3) PR SEMINAR
    4)
    ```

EZ.