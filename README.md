# Action Repository - GitHub Webhook Testing

This repository is used to test GitHub webhook events with the webhook receiver application.


## Webhook Configuration

The webhook is configured to send events to: `<your-ngrok-url>/webhook/receiver`

### Events Monitored:
- ✅ Push events
- ✅ Pull Request events (open)
- ✅ Pull Request events (closed/merged)

## Testing Instructions

### 1. Test Push Event
```bash
echo "Test push" >> test.txt
git add .
git commit -m "Test push event"
git push
```

### 2. Test Pull Request Event
```bash
# Create a new branch
git checkout -b feature-test
echo "Feature content" >> feature.txt
git add .
git commit -m "Add feature"
git push -u origin feature-test

# Create PR on GitHub: feature-test → main
```

### 3. Test Merge Event
```bash
# After creating the PR, merge it on GitHub
# This will trigger the merge event
```

## Verification

After triggering events, check the webhook receiver dashboard at:
`http://127.0.0.1:8080/webhook/`

Events should appear in the dashboard within 15 seconds (auto-refresh interval).

## Repository Links

- **webhook-repo**: https://github.com/Samee28/webhook-repo (Flask application)
- **action-repo**: https://github.com/Samee28/action-repo (This repository)

## Assessment Completion

This repository is part of the GitHub Webhook Receiver assessment task:
- [x] webhook-repo created with Flask application
- [x] action-repo created for testing webhooks
- [x] MongoDB integration with fallback support
- [x] UI dashboard with 15-second auto-refresh
- [x] Event formatting as per requirements
- [ ] Webhook configured (pending ngrok setup)
- [ ] Live testing with real GitHub events

---

 
