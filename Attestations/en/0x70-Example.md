# Example

The following is a full example of a CycloneDX attestation.

```json
{
  "bomFormat": "CycloneDX",
  "specVersion": "1.6",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "declarations": {
    "assessors": [
      {
        "bom-ref": "assessor-1",
        "thirdParty": true,
        "organization": {
          "name": "Assessors Inc"
        }
      }
    ],
    "attestations": [
      {
        "summary": "Attestation summary here",
        "assessor": "assessor-1",
        "map": [
          {
            "requirement": "requirement-1",
            "claims": [ "claim-1" ],
            "counterClaims": [ "counterClaim-1" ],
            "conformance": {
              "score": 0.8,
              "rationale": "Conformance rationale here",
              "mitigationStrategies": [ "mitigationStrategy-1" ]
            },
            "confidence": {
              "score": 1,
              "rationale": "Confidence rationale here"
            }
          }
        ],
        "signature": {
          "algorithm": "ES256",
          "certificatePath": [ "MIIB...", "MIID..." ],
          "value": "tqIT..."
        }
      }
    ],
    "claims": [
      {
        "bom-ref": "claim-1",
        "target": "acme-inc",
        "predicate": "Predicate here",
        "mitigationStrategies": [ "mitigationStrategy-1" ],
        "reasoning": "Reasoning here",
        "evidence": [ "evidence-1" ],
        "counterEvidence": [ "counterEvidence-1" ],
        "externalReferences": [
          {
            "type": "issue-tracker",
            "url": "https://alm.example.com"
          }
        ],
        "signature": {
          "algorithm": "ES256",
          "certificatePath": [ "MIIB...", "MIID..." ],
          "value": "tqIT..."
        }
      }
    ],
    "evidence": [
      {
        "bom-ref": "evidence-1",
        "propertyName": "internal.com.acme.someProperty",
        "description": "Description here",
        "data": [
          {
            "name": "Name of the data",
            "contents": {
              "attachment": {
                "content": "Evidence here",
                "contentType": "text/plain"
              }
            },
            "classification": "PII",
            "sensitiveData": [ "Describe sensitive data here" ]
          }
        ],
        "created": "2023-04-25T00:00:00+00:00",
        "expires": "2023-05-25T00:00:00+00:00",
        "author": {
          "name": "Mary"
        },
        "reviewer": {
          "name": "Jane"
        },
        "signature": {
          "algorithm": "ES256",
          "certificatePath": [ "MIIB...", "MIID..." ],
          "value": "tqIT..."
        }
      },
      {
        "bom-ref": "counterEvidence-1",
        "propertyName": "internal.com.acme.someProperty",
        "description": "Description here",
        "data": [
          {
            "name": "Name of the data",
            "contents": {
              "attachment": {
                "content": "Counter evidence here",
                "contentType": "text/plain"
              }
            },
            "classification": "Public",
            "sensitiveData": [ "Describe sensitive data here" ]
          }
        ],
        "created": "2023-04-25T00:00:00+00:00",
        "expires": "2023-05-25T00:00:00+00:00",
        "author": {
          "name": "Mary"
        },
        "reviewer": {
          "name": "Jane"
        },
        "signature": {
          "algorithm": "ES256",
          "certificatePath": [ "MIIB...", "MIID..." ],
          "value": "tqIT..."
        }
      },
      {
        "bom-ref": "mitigationStrategy-1",
        "propertyName": "internal.com.acme.someProperty",
        "description": "Description here",
        "data": [
          {
            "name": "Name of the data",
            "contents": {
              "attachment": {
                "content": "Mitigation strategy here",
                "contentType": "text/plain"
              }
            },
            "classification": "Company Confidential",
            "sensitiveData": [ "Describe sensitive data here" ]
          }
        ],
        "created": "2023-04-25T00:00:00+00:00",
        "expires": "2023-05-25T00:00:00+00:00",
        "author": {
          "name": "Mary"
        },
        "reviewer": {
          "name": "Jane"
        },
        "signature": {
          "algorithm": "ES256",
          "certificatePath": [ "MIIB...", "MIID..." ],
          "value": "tqIT..."
        }
      }
    ],
    "targets": {
      "organizations": [
        {
          "bom-ref": "acme-inc",
          "name": "Acme Inc"
        }
      ]
    },
    "affirmation": {
      "statement": "I certify, to the best of my knowledge, that all information is correct...",
      "signatories": [
        {
          "name": "Tom",
          "role": "CEO",
          "signature": {
            "algorithm": "ES256",
            "certificatePath": [ "MIIB...", "MIID..." ],
            "value": "tqIT..."
          }
        },
        {
          "name": "Jerry",
          "role": "COO",
          "organization": {
            "name": "Acme Inc"
          },
          "externalReference": {
            "type": "electronic-signature",
            "url": "https://example.com/coo-sig.png"
          }
        }
      ],
      "signature": {
        "algorithm": "ES256",
        "certificatePath": [ "MIIB...", "MIID..." ],
        "value": "tqIT..."
      }
    },
    "signature": {
      "algorithm": "ES256",
      "certificatePath": [ "MIIB...", "MIID..." ],
      "value": "tqIT..."
    }
  },
  "signature": {
    "algorithm": "ES256",
    "certificatePath": [ "MIIB...", "MIID..." ],
    "value": "tqIT..."
  }
}
```