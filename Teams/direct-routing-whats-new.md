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
description: Cet article décrit les nouveautés du routage direct. Revenez souvent à la recherche de mises à jour.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 85a700faf37044c97c432707b07b6d6699c6692b
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948581"
---
# <a name="whats-new-for-direct-routing"></a>Nouveautés du routage direct

Cet article décrit les nouveautés du routage direct. Revenez souvent à la recherche de mises à jour.

## <a name="new-direct-routing-sip-endpoints"></a>Nouveaux points de terminaison SIP de routage direct 

Microsoft va introduire de nouvelles adresses IP de signalisation vers les points de terminaison SIP de routage direct Teams. Pour vous assurer que cette modification n’affecte pas la disponibilité de votre service, assurez-vous que votre contrôleur de bordure de session et votre pare-feu sont configurés pour utiliser les sous-réseaux recommandés 52.112.0.0/14 et 52.120.0.0/14 pour la classification et les règles de liste de contrôle d’accès. Pour plus d’informations, consultez [Microsoft 365, Office 365 et Office 365 environnements GCC](direct-routing-plan.md#microsoft-365-office-365-and-office-365-gcc-environments).  

## <a name="trunk-demoting-logic-based-on-sip-options"></a>Logique de rétrogradation de jonction basée sur les options SIP

Une nouvelle fonctionnalité basée sur les options SIP est introduite pour l’intégrité de la jonction. Lorsqu’elle est activée dans la configuration de la passerelle (voir Set-CsOnlinePSTNGateway applet de commande et paramètre SendSipOptions), la logique de routage pour les appels sortants rétrograde les jonctions qui n’envoient pas régulièrement les options SIP (la période attendue est une option SIP envoyée par le SBC par minute) vers le serveur principal Microsoft. Ces jonctions rétrogradées sont placées à la fin de la liste des jonctions disponibles pour l’appel sortant et sont essayées comme les dernières; ce qui réduit potentiellement le temps de configuration des appels.
Toute jonction activée pour cette fonctionnalité qui n’envoie pas au moins une option SIP dans les cinq minutes à l’un des proxys SIP régionaux Microsoft (NOAM, EMEA, APAC, OCEA) est considérée comme rétrogradée. Si une jonction envoie des options SIP uniquement à un sous-ensemble de proxys SIP régionaux Microsoft, ces itinéraires sont essayés en premier et le reste est rétrogradé.


## <a name="sip-support"></a>Prise en charge SIP

Le 1er juin 2022, Microsoft supprimera la prise en charge des noms de domaine complets sip-all.pstnhub.microsoft.com et sip-all.pstnhub.gov.teams.microsoft.us de la configuration du routage direct.

Si aucune action n’est effectuée avant le 1er juin, les utilisateurs ne pourront pas passer ou recevoir des appels via le routage direct.

Pour éviter l’impact sur le service :

- Utilisez les sous-réseaux recommandés : (52.112.0.0/14 et 52.120.0.0/14) pour toutes les règles de classification ou de liste de contrôle d’accès.
- Arrêtez l’utilisation du nom de domaine complet sip-all lors de la configuration des contrôles de bordure de session pour le routage direct.

Pour plus d’informations, consultez [Planifier le routage direct](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificats TLS

Microsoft 365 met à jour Teams et d’autres services pour utiliser un autre ensemble d’autorités de certification racines.

Pour plus d’informations et pour obtenir la liste complète des services affectés, consultez [Modifications apportées aux certificats TLS des services Microsoft 365, y compris Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Autorités de certification

À compter du 1er février 2022, l’interface SIP de routage direct approuvera uniquement les certificats signés par les autorités de certification qui font partie du programme de certificats racines de confiance Microsoft. Effectuez les étapes suivantes pour éviter l’impact sur le service :

- Vérifiez que votre certificat SBC est signé par une autorité de certification qui fait partie du programme de certificat racine approuvé Microsoft.
- Vérifiez que l’extension Utilisation étendue de la clé (EKU) de votre certificat inclut « Authentification du serveur ».

Pour plus d’informations sur le programme de certificat racine approuvé Microsoft, consultez [Configuration requise du programme - Programme racine approuvé Microsoft](/security/trusted-root/program-requirements).

Pour obtenir la liste des autorités de certification [approuvées, consultez Liste des certificats d’autorité de certification incluses par Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Remplacer les en-têtes

À compter d’avril 2022, le routage direct rejette les demandes SIP pour lesquelles les en-têtes Replaces sont définis. Aucune modification n’est apportée aux flux dans lesquels Microsoft envoie l’en-tête Replaces au contrôleur de bordure de session (SBC).

Vérifiez vos configurations SBC et assurez-vous que vous n’utilisez pas d’en-têtes De remplacement dans les requêtes SIP.

## <a name="tls10-and-11"></a>TLS1.0 et 1.1

Pour fournir le meilleur chiffrement de sa catégorie à nos clients, Microsoft prévoit de déprécier les versions TLS (Transport Layer Security) 1.0 et 1.1. Le 3 avril 2022, Microsoft forcera l’utilisation de TLS1.2 pour l’interface SIP de routage direct.

Pour éviter tout impact sur le service, vérifiez que vos SBC sont configurés pour prendre en charge TLS1.2 et qu’ils peuvent se connecter à l’aide de l’une des suites de chiffrement suivantes :

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 par exemple ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 par exemple ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 par exemple ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 par exemple ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Rubriques connexes

- [Routage direct - Protocole SIP](direct-routing-protocols-sip.md)
