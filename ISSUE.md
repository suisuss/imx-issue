

# IMX Issue

## Contract Deployment

**Verified Contract:** [0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134](https://ropsten.etherscan.io/address/0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134B#code)

**Constructor Arguments:**
- `0xaf5a2653D0bFA61962Ce6Fe837a0B6c2a3a35d5A`
- `Asset`
- `ASS`
- `0x6C21EC8DE44AE44D0992ec3e2d9f1aBb6207D864`
  - [Ropsten registration address](https://github.com/immutable/imx-contracts) found in repo `README.md`

## Project Registration

`yarn onboarding:create-project`

**Result:**
```
INFO 2022-07-14T16:30:17+10:00 Creating project... | component=[IMX-CREATE-PROJECT] extra=undefined
REQUEST:
 POST https://api.ropsten.x.immutable.com/v1projects
RESPONSE:
 201 Created
INFO 2022-07-14T16:30:19+10:00 Created project with ID: 68359 | component=[IMX-CREATE-PROJECT] extra=undefined
Done in 3.54s.
```

**ProjectID:** 68359

## Collection Registration

**ENV:**
```
#=============================================
# Onboarding
#=============================================
OWNER_ACCOUNT_PRIVATE_KEY=ce8a5f21566f2b0c6eb355a6e8bad06234d352e4e91e08bfd8e0e42b1a315ec7
COLLECTION_CONTRACT_ADDRESS=0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134B
COLLECTION_PROJECT_ID=68359
```

`yarn onboarding:create-collection`

**Result:**
```
INFO 2022-07-14T16:38:37+10:00 Creating collection... | component=[IMX-CREATE-COLLECTION]
extra="0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134B"
REQUEST:
 POST https://api.ropsten.x.immutable.com/v1collections
RESPONSE:
 201 Created
INFO 2022-07-14T16:38:40+10:00 Created collection | component=[IMX-CREATE-COLLECTION] extra=undefined
{
  "address": "0xc7b5a11c4b21e0694c5e8f85d6e8be97a689134b",
  "name": "ENTER_COLLECTION_NAME",
  "description": "",
  "icon_url": "https://res.cloudinary.com/metakey/image/upload/v1654122837/app.themetakey.com/Royalities_u5atgg.png",
  "collection_image_url": "https://res.cloudinary.com/metakey/image/upload/v1654122837/app.themetakey.com/Royalities_u5atgg.png",
  "project_id": 68359,
  "project_owner_address": "",
  "metadata_api_url": "https://metakrew.mypinata.cloud/ipfs/QmXAyh8z1u22sd1R9gwZmr5mZMFafxbVkPjRV2oFuUNFJS"
}
Done in 5.15s.
```

## Metadata

**URL:** [https://metakrew.mypinata.cloud/ipfs/QmXAyh8z1u22sd1R9gwZmr5mZMFafxbVkPjRV2oFuUNFJS](https://metakrew.mypinata.cloud/ipfs/QmXAyh8z1u22sd1R9gwZmr5mZMFafxbVkPjRV2oFuUNFJS)

**Schema:**

```
[
      {
        name: 'name',
        type: MetadataTypes.Text

      },

      {
        name: 'description',
        type: MetadataTypes.Text
      },

      {
        name: 'image_url',
        type: MetadataTypes.Text
      },

      {
        name: 'attack',
        type: MetadataTypes.Discrete,
        filterable: true
      },

      {
        name: 'collectable',
        type: MetadataTypes.Boolean,
        filterable: true
      },

      {
        name: 'class',
        type: MetadataTypes.Enum,
        filterable: true
      }
      // ..add rest of schema here
]
```

`yarn onboarding:add-metadata-schema`

**Result:**
```
INFO 2022-07-14T16:43:01+10:00 Adding metadata schema to collection | component=[IMX-ADD-COLLECTION-METADATA-SCHEMA]
extra="0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134B"
REQUEST:
 POST https://api.ropsten.x.immutable.com/v1collections/0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134B/metadata-schema
RESPONSE:
 201 Created
INFO 2022-07-14T16:43:02+10:00 Added metadata schema to collection | component=[IMX-ADD-COLLECTION-METADATA-SCHEMA]
extra="0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134B"
{
  "result": "OK"
}
Done in 2.48s.
```

## Minting

**ENV:**

```
#=============================================
# Bulk Minting
#=============================================
PRIVATE_KEY1=ce8a5f21566f2b0c6eb355a6e8bad06234d352e4e91e08bfd8e0e42b1a315ec7
TOKEN_ID=1
TOKEN_ADDRESS=0xC7b5a11c4B21E0694C5e8f85D6E8Be97a689134B
BULK_MINT_MAX=50
```

`yarn bulk-mint -- -n 3 -w 0xaf5a2653D0bFA61962Ce6Fe837a0B6c2a3a35d5A`

**Result:**

```
tokenId
1
INFO 2022-07-14T16:46:52+10:00 MINTER REGISTRATION | component=imx-bulk-mint-script extra=undefined
ERROR 2022-07-14T16:46:52+10:00 {"code":"account_stark_key_already_registered","message":"Stark key already registered"} | component=imx-bulk-mint-script extra=undefined
Error: {"code":"account_stark_key_already_registered","message":"Stark key already registered"}
    at f (/home/suisuss/programming/work/others/NewGanymedeResearch/IMX/registration/node_modules/@imtbl/imx-sdk/src/libs/utils.ts:29:12)
    at /home/suisuss/programming/work/others/NewGanymedeResearch/IMX/registration/node_modules/@imtbl/imx-sdk/node_modules/fp-ts/es6/Either.js:419:30
    at processTicksAndRejections (internal/process/task_queues.js:95:5)
error Command failed with exit code 1.

```

## Conclusion

i'm following all the instructions supplied in the article you've sent correctly, aswell as what is mentioned in [https://github.com/immutable/imx-contracts](https://github.com/immutable/imx-contracts) and [https://docs.x.immutable.com/docs/onboarding](https://docs.x.immutable.com/docs/onboarding).

