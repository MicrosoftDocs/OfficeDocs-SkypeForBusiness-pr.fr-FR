---
title: Planifier une file d’attente d’appels sur le Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Vue d’ensemble de l’utilisation d’un standard automatique Cloud avec Skype entreprise Server 2019.
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221304"
---
# <a name="plan-cloud-call-queues"></a>Planifier les files d’attente des appels Cloud

La file d’attente des appels sur le Cloud est un service qui accepte les appels client, lit un message d’accueil, puis passe ces appels dans une file d’attente lors de la recherche d’une liste préconfigurée d’agents pour répondre à ces appels. Vous pouvez définir l’ensemble des agents dans les listes de distribution ou les groupes de sécurité à extension messagerie. Votre organisation peut avoir une ou plusieurs files d’attente d’appels. Les files d’attente d’appels sont généralement utilisées en combinaison avec des standards automatiques.

En outre, les files d’attente d’appels Cloud peuvent fournir les éléments suivants :

- Musique pendant que les appelants sont en attente
- Paramètres personnalisés pour la taille maximale, le délai d’expiration et les options de traitement des appels de la file d’attente d’appels

Chaque file d’attente est affectée à un **compte de ressource** (voir [Configure Resource Accounts](configure-onprem-ra.md)) sur votre système Skype entreprise Server 2019 qui sera lié directement à une file d’attente d’appels dans le centre d’administration Microsoft Teams. Pour plus d’informations sur les files d’attente d’appels et sur les options et les fonctionnalités disponibles pour les files d’attente d’appels, voir [Create a Cloud Call queue](/MicrosoftTeams/create-a-phone-system-call-queue) .

> [!NOTE]
> Vous pouvez affecter plusieurs numéros de téléphone à une file d’attente d’appels, mais il doit s’agir de numéros de service Microsoft, de numéros de routage directs ou de numéros hybrides.

## <a name="requirements"></a>Configuration requise

La configuration requise suivante suppose que vous ayez déjà déployé Skype entreprise Server 2019 dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Pour une nouvelle configuration de files d’attente d’appels sur le Cloud, suivez les étapes décrites dans [Configure Resource Accounts](configure-onprem-ra.md). Vous devrez créer des comptes de ressources en ligne ou dans Skype entreprise Server 2019, et vous devrez peut-être également associer un numéro de téléphone à la file d’attente d’appels.

En plus de la configuration requise ci-dessus, les conditions suivantes doivent être configurées pour se connecter au service de file d’attente des appels de Microsoft Cloud :

- Connectivité hybride. Si vous avez déjà déployé Skype entreprise Server et que vous souhaitez activer les files d’attente d’appels dans le Cloud pour vos utilisateurs locaux, vous devez vous assurer que la connectivité hybride est configurée entre vos environnements locaux et en ligne. Il s’agit parfois d’une configuration de domaine fractionné.

   Pour plus d’informations, reportez-vous à la rubrique [plan Hybrid Connectivity between Skype for Business Server et microsoft 365 ou office 365](plan-hybrid-connectivity.md) et configuration de la [connectivité hybride entre Skype entreprise server et Microsoft 365 ou Office 365](configure-hybrid-connectivity.md).

- Si vous affectez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence utilisateur virtuelle du système téléphonique économique. Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation et vous permet de créer des fonctionnalités de standard automatique et de file d’attente d’appel.

- Créez un [compte de ressource](configure-onprem-ra.md) local pour chaque file d’attente d’appels et attribuez une licence et un numéro de téléphone si nécessaire.  

## <a name="additional-planning-resources"></a>Ressources de planification supplémentaires

Le didacticiel intitulé [petite entreprise-configurer un standard automatique](/microsoftteams/tutorial-org-aa) passe par le processus de collecte d’informations sur les besoins des utilisateurs, de la planification d’une structure de standards automatiques et d’utilisateurs (et éventuellement d’appels de files d’attente), de l’écriture des invites de menu et de l’implémentation du plan dans le centre d’administration en ligne. consultez le didacticiel et utilisez les exercices t créer votre plan.

Lorsque vous disposez d’une structure solide qui répond à vos besoins et d’un script qui guide les clients de manière efficace, passez à la [Configuration des comptes de ressources](configure-onprem-ra.md).

## <a name="see-also"></a>Voir aussi

[Configurer des comptes de ressources](configure-onprem-ra.md)

[Activer l'enregistrement des invites personnalisées à l'aide de l'interface utilisateur de téléphonie](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Un standard Cloud automatique, qu’est-ce que c’est ?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planification de la connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](plan-hybrid-connectivity.md)

[Configuration de la connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](configure-hybrid-connectivity.md)

[Gérer les comptes de ressources dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
