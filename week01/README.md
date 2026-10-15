# 🚀 8주 개발 외주 준비

현업 웹개발 경험을 기반으로  

소규모 개발 외주를 독립적으로 수행하기 위한 학습 기록입니다.

## 목표

요구사항 분석  

→ Figma 화면설계  

→ DB 설계  

→ 개발  

→ 테스트  

→ Docker 배포  

→ 유지보수

## Tech Stack

- PHP 8
- Laravel
- Vue 3
- MySQL
- Python
- FastAPI
- Docker
- Git
- Figma

## 8 Week Plan

| Week | Topic | Status |

|---|---|---|

| Week 01 | PHP 8 / Laravel / Git / Docker | 🔄 |

| Week 02 | Laravel CRUD | ⬜ |

| Week 03 | Vue 3 Admin | ⬜ |

| Week 04 | Reservation Management | ⬜ |

| Week 05 | Python / FastAPI Automation | ⬜ |

| Week 06 | Docker Deployment | ⬜ |

| Week 07 | Figma Planning | ⬜ |

| Week 08 | Portfolio / Freelance | ⬜ |

## Portfolio Goal

1. Reservation Management System
2. Excel Automation System
3. Web Maintenance Case Study

## 2026-10-15 작업 기록

### 오늘 작업

- Laravel 13 프로젝트 생성
- PHP 8.4-fpm Docker 환경 구성
- Nginx 8088 포트 구성
- MySQL 8.0 3308 포트 구성
- Laravel과 MySQL 연결
- migration 정상 확인
- `localhost:8088` Laravel 기본 화면 정상 확인

### Troubleshooting

#### 1. PHP 8.3에서 Composer dependency 버전 오류

- **증상:** PHP 8.3에서 Composer dependency 버전 오류가 발생했다.
- **원인:** PHP 8.3이 프로젝트 의존성 버전 조건을 만족하지 못했다.
- **해결:** Docker PHP 이미지를 `php:8.4-fpm`으로 변경했다.
- **확인:** Composer 의존성 설치가 오류 없이 완료되었다.

#### 2. MySQL Access denied

- **증상:** Laravel에서 MySQL 접속 시 `Access denied`가 발생했다.
- **원인:** `.env`의 `DB_DATABASE`, `DB_USERNAME`이 MySQL에 만든 `laravel`과 대소문자가 달랐다.
- **해결:** 두 값을 `laravel` 소문자로 통일한 뒤 `php artisan config:clear`, `php artisan cache:clear`를 실행했다.
- **확인:** migration이 정상 실행되었다.

#### 3. tempnam storage 권한 오류

- **증상:** `tempnam()` storage 권한 오류가 발생했다.
- **원인:** PHP 프로세스가 `storage/framework`와 `bootstrap/cache`에 쓸 수 없었다.
- **해결:** `storage/framework`와 `bootstrap/cache` 권한을 수정했다.
- **확인:** `localhost:8088`에서 Laravel 기본 화면이 정상 표시되었다.

