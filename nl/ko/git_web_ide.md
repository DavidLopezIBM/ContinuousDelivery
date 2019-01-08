---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-29"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:download: .download}

# Eclipse Orion Web IDE에서 Git에 대해 작업
{: #git_web_ide}

{{site.data.keyword.webide}}에서 다수의 공통 Git 명령을 실행할 수 있습니다.

코딩 위치와 상관없이 이 빠른 참조서를 통해 일반 태스크를 수행할 수 있습니다.  가능한 경우 Git 명령은 Web IDE에 있는 동등한 항목과 함께 표시됩니다. 

## 로컬 분기 작성
{: #create_branch}

### Eclipse Orion Web IDE
{: #create_branch_web}

1. **참조** 목록을 클릭하십시오.

1. **새 분기**를 클릭하십시오.

2. 분기 이름을 입력하고 **제출**을 클릭하십시오.

### Git 터미널
{: #create_branch_cmd}
1. `git branch<branchname>`를 입력하고 Enter를 누르십시오.

## 로컬 분기 작업
{: #start_working_on_branch}

### Eclipse Orion Web IDE
{: #start_working_on_branch_web}
1. **참조** 목록을 클릭하고 **로컬**을 펼치십시오.

2. 수정할 분기에 대해 체크아웃 아이콘 <img  class="inline" src="./images/checkout.png" alt="체크아웃 아이콘">을 클릭하십시오.

1. 선택한 분기가 **참조** 목록에 표시되는지 확인하십시오.

### Git 터미널
{: #start_working_on_branch_cmd}
1. 로컬 분기를 보려면 `git branch -l`를 입력하고 Enter를 누르십시오.

2. `git checkout<branchname>`을 입력하고 Enter를 누르십시오.


## 원격 분기의 변경사항을 포함하도록 로컬 분기 업데이트
{: #update_branch}

### Eclipse Orion Web IDE
{: #update_branch_web}

1. **동기화**를 클릭하십시오.

1. 충돌이 발생하면 [해결](#resolve_a_rebase_conflict)하십시오.

### Git 터미널
{: #update_branch_cmd}

1. `git pull`을 입력하고 Enter를 누르십시오.

## 로컬 분기 삭제
{: #delete_branch}

### Eclipse Orion Web IDE
{: #delete_branch_web}
1. 삭제할 분기가 체크아웃되지 않도록 하십시오. 이 분기가 체크아웃된 경우 [다른 분기를 체크아웃](#start_working_on_branch)하십시오.

1. **참조** 목록을 클릭하고 **로컬**을 펼치십시오.

2. 제거할 로컬 분기에 대해 **삭제** <img class="inline"  src="./images/delete.png" alt="삭제 아이콘">을 클릭하십시오.

### Git 터미널
{: #delete_branch_cmd}

1. `git branch -d<branchname>`를 입력하고 Enter를 누르십시오.

##원격 분기에 로컬 변경사항을 강제로 푸시
{: #force_push}

참조된 원격 분기의 컨텐츠를 활성 로컬 분기의 컨텐츠로 겹쳐쓰십시오.

원격 분기에 로컬 분기를 강제로 푸시하면 원격 분기에서 커미트를 유실할 수 있습니다.
{: important}

### Eclipse Orion Web IDE
{: #force_push_web}

1. 작업 디렉토리 변경 섹션의 출력 섹션에서 **푸시**에 대한 화살표를 클릭하십시오.
2. **분기 푸시 강제 실행**을 클릭하십시오.
3. 경고를 확인하십시오.

### Git 터미널
{: #force_push_cmd}

1. `git push <origin> <remote branch> -f`를 입력하고 Enter를 누르십시오.

## 활성 로컬 분기에서 스테이징되지 않은 변경사항 버리기
{: #discard_changes}

### Eclipse Orion Web IDE
{: #discard_changes_web}

1. 작업 디렉토리 변경 섹션에서 버리려는 변경사항이 있는 수정된 각 파일의 선택란을 선택하십시오.
2. 체크아웃 아이콘 <img class="inline"  src="./images/discard.png" alt="모든 변경사항을 버리고 선택한 파일을 체크아웃함">을 클릭하십시오.

### Git 터미널
{: #discard_changes_cmd}

1. `git checkout -- path/to/file/filename`을 입력하여 파일의 변경사항을 버리십시오.

## 파일을 커미트하고 원격 분기에 푸시
{: #commit}

### Eclipse Orion Web IDE
{: #commit_web}

1. 작업 디렉토리 변경 섹션에서 커미트할 각 파일의 선택란을 선택하십시오.

2. **커미트 메시지 입력** 필드에 변경사항을 설명하는 메시지를 입력하십시오.

  자세한 커미트 메시지를 제공하십시오. 자세한 정보가 없어도 변경이 필요한 이유를 이해할 수 있도록 메시지에서 충분한 세부사항을 제공해야 합니다. 도움이 되도록 팀의 문제 트래커에 있는 항목의 링크를 포함시킬 수 있습니다. 커미트 메시지의 첫 번째 행에는 50자 미만이 포함되어 있습니다. 다른 텍스트를 추가하기 전에 빈 행을 추가하십시오.
  {: tip}

3. **커미트**를 클릭하십시오.

4. **푸시**를 클릭하십시오.

### Git 터미널
{: #commit_cmd}

1. `git status`를 입력하고 Enter를 누르십시오.

2. 커미트할 변경사항을 검토하십시오. 커미트할 모든 파일이 나열되면 진행하십시오. 스테이징되지 않은 파일을 커미트하려면 먼저 스테이징하십시오.

3. `git commit`를 입력하고 Enter를 누르십시오.

4. 커미트 요약을 입력하고 빈 행을 추가한 다음 커미트 설명을 추가하십시오.

  커미트 요약은 50자 미만이어야 합니다. 자세한 정보가 없어도 변경이 필요한 이유를 이해할 수 있도록 커미트 설명에서 충분한 세부사항을 제공해야 합니다. 도움이 되도록 팀의 문제 트래커에 있는 항목의 링크를 포함시킬 수 있습니다.
  {: tip}

5. 커미트 메시지를 저장하십시오.

  커미트 메시지를 저장하고 기본 텍스트 편집기일 수 있는 Vim을 닫으려면 Esc를 누르고 `:wq`를 입력한 다음 Enter를 누르십시오.
  {: tip}

4. `git push`를 입력하고 Enter를 누르십시오.

## 커미트 히스토리 보기
{: #view_commit_history}

### Eclipse Orion Web IDE
{: #view_commit_history_web}

1. 활성 분기 섹션에서 **히스토리**를 펼쳐 해당 분기의 커미트 히스토리를 보십시오.

  커미트 히스토리는 연결된 시각적 그래프로도 볼 수 있습니다.

1. **그래픽 표시 전환** 아이콘 <img  class="inline" src="./images/graphicalhistoryicon.png" alt="그래픽 히스토리 아이콘">을 클릭하십시오.

  전환되면 활성 분기의 모든 수신 또는 출력 변경사항과 커미트 히스토리를 연결된 그래프로 그립니다.  시각적 표현에서 모든 커미트와 해당 커미트를 수행한 분기를 표시합니다.

  <img class="screen-shot" src="./images/visualhistoryexample.png" alt="가상 커미트 히스토리">

### Git 터미널
{: #view_commit_history_cmd}

1. `git log`를 입력하고 Enter를 누르십시오.

2. 커미터의 커미트를 찾아보십시오.
 * 추가 항목을 보려면 다음 페이지를 누르십시오.
 * 이전 항목을 보려면 이전 페이지를 누르십시오.

3. 항목 표시를 중지하려면 Q를 누르십시오.

## 커미트를 통해 도입된 변경 비교
{: #compare_changes}

### Eclipse Orion Web IDE
{: #compare_changes_web}

1. 커미트 히스토리를 보고 커미트를 찾으십시오. 자세한 정보는 [커미트 히스토리 보기](#view_commit_history)를 참조하십시오.

2. 커미트를 클릭하여 커미트의 세부사항을 보십시오.

3. 파일의 변경사항을 검토하려면 **>**을 클릭하십시오.

  커미트를 통해 행이 변경된 경우 원래 행은 음영 처리된 분홍색이 되고 새 행은 음영 처리된 초록색이 됩니다.  마찬가지로 커미트를 통해 추가된 행은 음영 처리된 초록색이고 커미트를 통해 제거된 행은 음영 처리된 분홍색입니다.
  {: tip}

### Git 터미널
{: #compare_changes_cmd}

1. `git log -p`를 입력하고 Enter를 누르십시오.

  **참고:** 특정 수의 커미트만 보려면 `git log -p -<number_of_commits_to_view>`를 입력하십시오.

2. 커미트를 탐색하십시오.
 * 추가 항목을 보려면 다음 페이지를 누르십시오.
 * 이전 항목을 보려면 이전 페이지를 누르십시오.

3. 변경사항을 검토하십시오.

  커미트를 통해 행이 변경되면 원래 행은 빨간색 텍스트로 표시되고 빼기 부호(-)로 시작됩니다. 새 행은 초록색 텍스트로 표시되며 더하기 부호(+)로 시작됩니다.  마찬가지로 커미트를 통해 추가된 행은 초록색 텍스트로 표시되며 +로 시작됩니다. 커미트를 통해 제거된 행은 빨간색 텍스트로 표시되고 -로 시작됩니다.
  {: tip}

1. 항목 표시를 중지하려면 Q를 누르십시오.

## 마지막 커미트 수정
{: #modify_last_commit}

  원격 저장소에 푸시한 다음 마지막 커미트를 수정하면 커미트 히스토리를 다시 씁니다. 이 변경사항은 커미트에 실패하거나 프로젝트의 다른 기여자에 또 다른 문제점을 일으킬 수 있습니다. 원격 저장소에 푸시한 커미트를 수정하기 전에 수행하는 내용을 알고 있어야 합니다.
  {: important}

### Eclipse Orion Web IDE
{: #modify_last_commit_web}
1. 커미트에 추가할 항목의 선택란을 선택하십시오.

1. **이전 커미트 수정** 선택란을 선택하십시오.

2. 필요하면 새 커미트 메시지를 입력하십시오.

3. **커미트**를 클릭하십시오.

### Git 터미널
{: #modify_last_commit_cmd}

1. 상태를 확인하십시오. 필요하면 파일을 스테이징하거나 스테이징을 해제하십시오.

2. `git commit --amend`를 입력하고 Enter를 누르십시오.

3. 텍스트 편집기에서 커미트 메시지를 승인하거나 수정하십시오.

  커미트 메시지를 저장하고 기본 텍스트 편집기일 수 있는 Vim을 닫으려면 Esc를 누르고 `:wq`를 입력한 다음 Enter를 누르십시오.
  {: tip}

## 커미트 태그 지정
{: #tag_commit}

### Eclipse Orion Web IDE
{: #tag_commit_web}

1. 커미트 히스토리를 보고 커미트를 찾으십시오. 자세한 정보는 [커미트 히스토리 보기](#view_commit_history)를 참조하십시오.

2. 커미트를 클릭하여 커미트의 세부사항을 보십시오.

3. 커미트 분할창에서 **커미트의 태그 작성** <img class="inline"  src="./images/tag.png" alt="커미트의 태그 작성">을 클릭하십시오.

4. 이름 필드에 태그 텍스트를 입력하십시오. **제출**을 클릭하십시오.

### Git 터미널
{: #tag_commit_cmd}

1. 커미트 히스토리를 보고 태그를 지정할 커미트의 ID를 얻으십시오. 자세한 정보는 [커미트 히스토리 보기](#view_commit_history)를 참조하십시오.

2. `git tag -a<tag_text> <commit_id>`를 입력하고 Enter를 누르십시오.

## 커미터 이름 및 이메일 주소 변경
{: #change_the_committer_name_and_email_address}

### Eclipse Orion Web IDE
{: #change_info_web}
1. 구성 아이콘 <img class="inline" src="./images/configurations.png" alt="구성 아이콘">을 클릭하십시오.

2. user.email 및 user.name 값을 업데이트하여 사용자 이메일 주소와 이름을 변경하십시오. **제출**을 클릭하여 각 변경을 저장하십시오.

### Git 터미널
{: #change_info_cmd}

단일 저장소의 이름과 이메일 주소를 업데이트하려면 다음을 수행하십시오.

1. `git config user.email "<your@email.com>"`을 입력하고 Enter를 누르십시오.

2. `git config user.name "<Your Name>"`을 입력하고 Enter를 누르십시오.

모든 저장소의 이름과 이메일 주소를 업데이트하려면 다음을 수행하십시오.

1. `git config --global user.email "<your@email.com>"`을 입력하고 Enter를 누르십시오.

2. `git config --global user.name "<Your Name>"`을 입력하고 Enter를 누르십시오.

##커미트 되돌리기
{: #revert}

커미트가 활성 분기에 도입한 변경사항을 되돌리십시오.

### Eclipse Orion Web IDE
{: #revert_web}

1. 히스토리에서 커미트를 선택하십시오.

2. 되돌리기 아이콘 <img class="inline" src="./images/revert.png" alt="되돌리기 아이콘">을 클릭하십시오.

### Git 터미널
{: #revert_cmd}

1. `git revert <commit ID>`를 입력하고 Enter를 누르십시오.

## 변경사항 병합
{: #merge_changes}

소스 분기에서 대상 분기로 변경사항을 전달해야 하는 경우 먼저 병합해야 합니다. 일반적으로 소스 분기는 변경을 수행한 분기이고 대상 분기는 마스터 분기입니다.

### Eclipse Orion Web IDE
{: #merge_changes_web}

1. 병합할 분기를 결정하십시오.

2. 대상 분기를 체크아웃하십시오. 자세한 정보는 [ 로컬 분기에 대한 작업](#start_working_on_branch)을 참조하십시오.

 <img class="screen-shot" src="./images/destinationbranch.png" alt="대상 분기 체크아웃">

1. **참조** 목록을 클릭하고 **로컬**을 펼친 다음 소스 분기의 이름을 클릭하십시오. 소스 분기의 변경사항은 수신 섹션에 표시됩니다.

  <img class="screen-shot" src="./images/sourcebranch.png" alt="수신 섹션에 표시된 소스 분기의 변경사항">

1. 수신 섹션에서 **병합** 아이콘 <img  class="inline" src="./images/mergeicon.png" alt="수신 섹션의 병합 아이콘">을 클릭하십시오.

1. **참조** 목록에서 방금 변경사항을 병합한 분기에 대해 체크아웃 아이콘을 클릭하십시오.

1. 변경사항을 전달하려면 **푸시**를 클릭하십시오. 그렇지 않으면 이때 테스트 배치를 작성하여 모두가 제대로 작동하는지 확인할 수 있습니다.

### Git 터미널
{: #merge_changes_cmd}

1. 병합할 분기를 결정하십시오.

2. 대상 분기를 체크아웃하십시오. 자세한 정보는 [ 로컬 분기에 대한 작업](#start_working_on_branch)을 참조하십시오.

3. `git merge <source_name>`를 입력하고 Enter를 누르십시오.


## 병합 충돌 해결
{: #resolve_a_merge_conflict}

### Eclipse Orion Web IDE
{: #resolve_a_merge_conflict_web}

1. 변경된 파일 분할창에서 충돌을 포함하는 파일 목록을 검토하십시오.

2. Web IDE에서 충돌이 포함된 각 파일을 여십시오.

3. 충돌하는 각 변경을 해결하십시오. 유지하지 않으려는 모든 텍스트를 삭제하십시오. 각 충돌의 형식은 다음과 같습니다.

		<<<<<<< HEAD
		체크아웃한 분기의 텍스트.
		=======
		Text in merged branch.
		>>>>>>> commit_ID_from_merged_branch
		
4. 충돌하는 각 파일의 선택란을 선택하십시오. 병합 커미트 메시지를 입력하고 **커미트**를 클릭하십시오.

### Git 터미널
{: #resolve_a_merge_conflict_cmd}

1. 충돌을 포함하는 파일에서 이름의 Git 메시지를 검토하십시오.

2. 텍스트 편집기에서 충돌을 포함하는 파일을 여십시오.

3. 충돌하는 각 변경을 해결한 다음 파일을 저장하십시오. 유지하지 않으려는 모든 텍스트를 삭제하십시오. 각 충돌의 형식은 다음과 같습니다.

		<<<<<<< HEAD
		체크아웃한 분기의 텍스트.
		=======
		Text in merged branch.
		>>>>>>> merged_branch
		
4. 수정한 각 파일을 스테이징한 다음 병합을 커미트하십시오.

## 분기 리베이스
{: #rebase_branches}

### Eclipse Orion Web IDE
{: #rebase_branches_web}

1. 리베이스할 분기를 결정하십시오. 소스 분기의 컨텐츠를 대상 분기로 리베이스합니다.

2. 대상 분기를 체크아웃하십시오. 자세한 정보는 [ 로컬 분기에 대한 작업](#start_working_on_branch)을 참조하십시오.

1. **참조** 목록을 클릭하십시오.

1. 소스 분기의 이름을 클릭하십시오.

1. 수신 섹션에서 리베이스 아이콘 <img  class="inline" src="./images/rebase.png" alt="리베이스 아이콘">을 클릭하십시오.

5. 충돌이 발생하면 [해결](#resolve_a_rebase_conflict)하십시오.

6. 필요한 수만큼 이전 단계를 반복하여 리베이스 조작을 완료하십시오.

1. **참조** 목록을 클릭하고 **원본**을 펼친 다음 소스 분기의 이름을 클릭하십시오.

1. **푸시**를 클릭하십시오.

### Git 터미널
{: #rebase_branches_cmd}

1. `git checkout <destination_branchname>`을 입력하고 Enter를 눌러 업데이트할 분기를 체크아웃하십시오.

2. `git rebase <source_branchname>`를 입력하고 Enter를 누르십시오.

3. 충돌이 발생하면 [해결](#resolve_a_rebase_conflict)하십시오.

4. 필요한 수만큼 이전 단계를 반복하여 리베이스 조작을 완료하십시오.

  리베이스 조작을 중지하려면 `git rebase --abort`를 입력하고 Enter를 누르십시오.
  {: tip}

## 리베이스 충돌 해결
{: #resolve_a_rebase_conflict}

### Eclipse Orion Web IDE
{: #resolve_a_rebase_conflict_web}

1. 작업 디렉토리 변경 섹션에서 충돌하는 파일 목록을 검토하십시오.

2. Web IDE에서 충돌이 포함된 각 파일을 여십시오.

3. 충돌하는 각 변경을 해결하십시오. 유지하지 않으려는 모든 텍스트를 삭제하십시오. 각 충돌의 형식은 다음과 같습니다.

		<<<<<<< HEAD
		체크아웃한 분기의 텍스트.
		=======
		Text in merged branch.
		>>>>>>> commit_ID_from_merged_branch
		{: tip}
4. 리베이스 분할창에서 정정된 각 파일의 선택란을 선택하고 **계속**을 클릭하십시오.

### Git 터미널
{: #resolve_a_rebase_conflict_cmd}

1. 충돌을 포함하는 파일에서 이름의 Git 메시지를 검토하십시오.

2. 텍스트 편집기에서 충돌을 포함하는 파일을 여십시오.

3. 충돌하는 각 변경을 해결한 다음 파일을 저장하십시오. 유지하지 않으려는 모든 텍스트를 삭제하십시오. 각 충돌의 형식은 다음과 같습니다.

		<<<<<<< HEAD
		체크아웃한 분기의 텍스트.
		=======
		Text in merged branch.
		>>>>>>> merged_branch
		
4. 수정한 각 파일을 스테이징하십시오.

5. `git rebase --continue`를 입력하고 Enter를 눌러 리베이스 작업을 재개하십시오.
