# Rake Fees distribution system

## Actors

* Validators
* Stakers
* Rake Fees

* Validator group build from multiple validators

Weight is based on how much fury is staked with that validator

The internal next weight counter is incremented with every deposit on behalf of the validator

### Withdrawal

When funds are withdrawn, the validators weight is set to internal next weight, and internal next
weight is reset to 1


## Proxy Contract

### Instantiate

```
{
    "onwer": "onwer_addr",
    "weight": 20,
    "denom": "STAR"
}
```

### Execs

#### Donate

```
{
    "donate": {}
}
```

#### Whithdraw

Only by owner

```
{
    "withdraw": {
        "receiver": "receiver_addrs",
        "amount": 10
    }
}
```

#### Close

Only by owner

```
{
    "close": {}
}
```

#### Propose Member

Only by owner
```
{
    "propose_member": {
        "member_addr"
    }
}
```

#### Update weight

```
{}
```

### Quries

#### Owner

```
{
    "owner": {}
}

{
    "addr": "owner_addr",
    "weight": 20
}
```

#### Is Closed

```
{
    "is_closed": {}
}
```

## Distribute

### Instantiate

```
{}
```

### Distribute

```
{
    "distribute": {}
}
```


### Withdraw

```
{
    "weight": 20,
    "diff": -10
}
```

### New Member

```
{
    "new_member": {
        "weight": 20
    }
}
```

## Membership

### Instantiate

This should receive the whole system config

```
{
    "proxy_code_id": 1024,
    "distribute_code_id": 1025
}
```

### Execs

#### Propose

```
{
    "addr": "member_addr"
}
```

### Query

#### Is Member

```
{
    "is_member": {
        "addr": "proxy_addr"
    }
}
```
