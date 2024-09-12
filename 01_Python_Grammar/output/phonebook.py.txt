1. 입출력 정의: 문자열, 딕셔너리 K:V
2.인터페이스: input()
3. 구조: while 반복문, 6개 기능을 구현 if 분기문 
4. 기능 구현 + 인터페이스 정책 
 
contact{}


while True:
    print('------전화번호부 프로그램------')
    print('1.추가 2.조회 3.검색 4.수정 5.삭제  9.종료')
    menu = int(input('메뉴를 선택해주세요.(숫자: only) : '))
    if  menu == 1: #연락처 추가 
        print('연락처 추가')
        new_name = input('이름: ')
        new_tel = input('전화번호: ')
        print(new_name, new_tel)
        
        #contact[new_name] = new_tel
        contact.setdefault(new_name, new_tel)
            
    elif  menu == 2: #연락처 조회 
        print('연락처 조회')
        #print(contact)
        for name, tel in contact.items():
            print(name, ':', tel)


    
    elif  menu == 3: #연락처 검색 
        print('연락처 검색')
        search_name = input('검색 이름: ')
        print(contact.get(search_name, '없는 이름입니다.'))
        #print(contact[search_name])
    
    elif  menu == 4: #연락처 수정
        print('연락처 수정')
        mod_name = input('수정 이름 : ')
        

        if mod_name in contact:
            mod_tel = input('새 전화번호: ')
            contact[mod_name] = mod_tel
        else: 
            print('등록되지 않은 이름입니다.')
            
    elif  menu == 5: #연락처 삭제
        print('연락처 삭제')
        del_name = input('삭제 이름 : ')
        
        if del_name in contact:
            del contact[del_name]
        else: 
            print('등록되지 않은 이름입니다.')
    elif  menu == 9: #연락처 종료 
        print('연락처 종료')
        break
    else: 
        print('잘못된 입력입니다.')
