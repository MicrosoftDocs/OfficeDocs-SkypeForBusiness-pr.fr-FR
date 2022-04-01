---
title: Nouveautés du routage direct
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Cet article décrit les nouveautés du routage direct. Consultez régulièrement les mises à jour.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53a1c2730ebf6db06fb92ac2fc4e0873563c98ce
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584328"
---
# <a name="whats-new-for-direct-routing"></a>Nouveautés du routage direct

Cet article décrit les nouveautés du routage direct. Consultez régulièrement les mises à jour.

## <a name="sip-support"></a>Prise en charge SIP

Le 1er juin 2022, Microsoft supprimera la prise en charge des FQDN sip-all.pstnhub.microsoft.com et sip-all.pstnhub.gov.teams.microsoft.us de la configuration du routage direct.

Si aucune action n’est prise avant le 1er juin, les utilisateurs ne pourront pas effectuer ni recevoir d’appels via un routage direct.

Pour éviter l’impact sur le service :

- Utilisez les sous-réseaux recommandés : (52.112.0.0/14 et 52.120.0.0/14) pour toute classification ou règle de contrôle d’accès (ACL).
- Cessez d’utiliser le FQDN sip-all lors de la configuration des contrôles de bordure de session pour le routage direct.

Pour plus d’informations, voir [Planifier le routage direct](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificats TLS

Microsoft 365 mise à jour Teams et d’autres services de manière à utiliser un autre jeu d’autorités de certification racine.

Pour plus d’informations et une liste complète des services concernés, voir les modifications [apportées au certificat TLS en Microsoft 365 services,](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676) y Microsoft Teams.

## <a name="certificate-authorities"></a>Autorités de certification

À compter du 1er février 2022, l’interface SIP de routage direct n’truste que les certificats signés par les autorités de certification qui font partie du programme de certificat racine de confiance Microsoft. Pour éviter l’impact sur le service, prenez les mesures suivantes :

- Assurez-vous que votre certificat SBC est signé par une personne d’certification qui fait partie du Programme de certificat racine de confiance Microsoft.
- Vérifiez que l’extension EKU (Extended Key Usage) de votre certificat inclut « Authentification serveur ».

Pour plus d’informations sur le programme microsoft Trusted Root Certificate Program (Programme de certificat racine de confiance), voir [Program Requirements - Microsoft Trusted Root Program (Programme racine de confiance Microsoft](/security/trusted-root/program-requirements)).

Pour obtenir une liste d’autorisations d’enregistrement de confiance, voir [Liste des certificats d’autorisation d’certification Microsoft inclus](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Remplacer les en-têtes

À partir d’avril 2022, le routage direct rejettera les requêtes SIP dont les en-têtes remplacent ceux définis. Il n’y a aucune modification aux flux dans lequel Microsoft envoie l’en-tête Remplace l’en-tête du contrôleur de bordure de session (SBC).

Vérifiez vos configurations SBC et vérifiez que vous n’utilisez pas les en-têtes Remplacer dans les demandes SIP.

## <a name="tls10-and-11"></a>TLS1.0 et 1.1

Pour fournir le meilleur chiffrement de qualité à nos clients, Microsoft envisage de décliner la sécurité TLS (Transport Layer Security) version 1.0 et 1.1. Le 3 avril 2022, Microsoft forcera l’utilisation du TLS1.2 pour l’interface SIP de routage direct.

Pour éviter tout impact sur le service, assurez-vous que vos SBCs sont configurés pour prendre en charge TLS1.2 et peuvent se connecter à l’aide d’une des suites cipher suivantes :

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 c’est-à-dire ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 c’est-à-dire ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 c’est-à-dire ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 c’est-à-dire ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Sujets associés

- [Routage direct - Protocole SIP](direct-routing-protocols-sip.md)
