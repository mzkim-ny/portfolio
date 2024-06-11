# Tanghulu

SELECT 번호, 인허가일자, 상세영업상태명, 폐업일자
FROM [dbo].[regular_tang_closed_1]

UNION ALL

SELECT 번호, 인허가일자, 상세영업상태명, 폐업일자
FROM [dbo].[regular_tang_open_2]

UNION ALL

SELECT 번호, 인허가일자, 상세영업상태명, 폐업일자
FROM [dbo].[rest_tang_closed_3]

UNION ALL

SELECT 번호, 인허가일자, 상세영업상태명, 폐업일자
FROM [dbo].[rest_tang_open_4]
