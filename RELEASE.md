# Release Strategy & Versioning

## Versioning Scheme

VoxtrynAI follows [Semantic Versioning](https://semver.org/) (SemVer):

```
MAJOR.MINOR.PATCH
  |      |      └─ Backward-compatible bug fixes
  |      └──────── Backward-compatible features
  └─────────────── Incompatible API changes
```

### Examples
- `0.1.0` → `0.2.0` - New feature added
- `1.0.0` → `1.0.1` - Bug fix
- `1.0.0` → `2.0.0` - Breaking changes

---

## Release Timeline

### Development Cycle
- **Continuous** - Daily commits to `develop` branch
- **Sprint** - 2-week development sprints
- **RC** - Release Candidate testing (1 week)
- **Release** - Production release

### Release Schedule
- **Minor Releases** - Every 2-3 months
- **Patch Releases** - As needed for bug fixes
- **Major Releases** - Annually or when breaking changes required

---

## Branch Strategy

```
main (Production)
  ↑
  └─ release/v1.x.x (Release branches)
      ↑
      └─ develop (Development)
          ↑
          ├─ feature/feature-name
          ├─ bugfix/bug-name
          └─ hotfix/hotfix-name
```

### Branch Rules

| Branch | Purpose | Protection |
|--------|---------|-----------|
| `main` | Production | Requires PR, all checks pass |
| `develop` | Development | Requires PR, 1 approval |
| `release/*` | Release prep | Temporary, merged to main |
| `hotfix/*` | Critical fixes | Merged to main & develop |
| `feature/*` | New features | Delete after merge |

---

## Release Checklist

### Before Release
- [ ] Update version in `package.json`
- [ ] Update `CHANGELOG.md`
- [ ] Update `README.md` if needed
- [ ] Run full test suite
- [ ] Run security scan
- [ ] Get code review approval

### During Release
- [ ] Create release branch from `develop`
- [ ] Merge to `main` with merge commit
- [ ] Create GitHub release with tag
- [ ] Write release notes
- [ ] Deploy to production

### After Release
- [ ] Verify deployment
- [ ] Merge back to `develop`
- [ ] Announce on social media
- [ ] Monitor for issues
- [ ] Document any fixes

---

## Support Policy

| Version | Release Date | End of Life | Status |
|---------|--------------|------------|--------|
| 1.0.x   | 2024-06-08   | 2026-06-08 | Active |
| 0.9.x   | 2024-01-01   | 2025-06-08 | LTS    |
| < 0.9   | 2023-xx-xx   | 2024-01-01 | EOL    |

---

**Last Updated:** June 8, 2024
