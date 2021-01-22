---
title: Planifier une file d’attente d’appels cloud
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
description: Vue d’ensemble de l’utilisation d’un service de gestion automatique cloud avec Skype Entreprise Server 2019.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918740"
---
# <a name="plan-cloud-call-queues"></a>Planifier les files d’attente d’appels cloud

La file d’attente d’appels cloud est un service qui accepte les appels des clients, lit un message d’accueil, puis place ces appels dans une file d’attente lors de la recherche d’une liste pré-configurée d’agents pour répondre à ces appels. Vous pouvez définir l’ensemble des agents dans les listes de distribution à messagerie ou les groupes de sécurité. Votre organisation peut avoir une ou plusieurs files d’attente d’appels. Les files d’attente d’appels sont généralement utilisées en combinaison avec les attendants automatiques.

En outre, les files d’attente d’appels cloud peuvent fournir :

- Musique pendant l’attente des appelants
- Paramètres personnalisés pour la taille maximale de la file d’attente d’appels, le délai d’attente et les options de gestion des appels

Un compte de ressource **(voir** [Configurer](configure-onprem-ra.md)les comptes de ressources) est affecté à chaque file d’attente d’appels sur votre système Skype Entreprise Server 2019 qui sera lié directement à une file d’attente d’appels dans le Centre d’administration Microsoft Teams. Pour plus [d’informations sur](/MicrosoftTeams/create-a-phone-system-call-queue) les files d’attente d’appels et les options et fonctionnalités existantes pour les files d’attente d’appels, voir Créer une file d’attente d’appels cloud.

> [!NOTE]
> Vous pouvez affecter plusieurs numéros de téléphone à une file d’attente d’appels, mais il doit s’agit de numéros de service Microsoft, de numéros de routage direct ou de numéros hybrides.

## <a name="requirements"></a>Conditions requises

Les conditions suivantes supposent que Skype Entreprise Server 2019 est déjà déployé dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Pour une nouvelle configuration des files d’attente d’appels cloud, suivez les étapes décrites dans [Configurer les comptes de ressources.](configure-onprem-ra.md) Vous devrez créer des comptes de ressources en ligne ou dans Skype Entreprise Server 2019, et vous devrez peut-être également associer un numéro de téléphone à la file d’attente d’appels.

Outre la configuration requise ci-dessus, les conditions ci-dessous doivent être configurées pour se connecter au service de file d’attente des appels Microsoft Cloud :

- Connectivité hybride. Si Skype Entreprise Server est déjà déployé et que vous souhaitez activer les files d’attente d’appels cloud pour vos utilisateurs locaux, vous devez vous assurer que la connectivité hybride est définie entre vos environnements locaux et en ligne. Il s’agit parfois d’une configuration de domaine fractionnement.

   Pour plus d’informations, voir Planifier la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) et configurer la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md)

- Si vous affectez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence d’utilisateur virtuel du système téléphonique sans frais. Cela offre des fonctionnalités de système téléphonique pour les numéros de téléphone au niveau de l’organisation, et vous permet de créer des fonctionnalités de numéro de téléphone et de attendant automatique.

- Créez un compte de ressource [local](configure-onprem-ra.md) pour chaque file d’attente d’appels et attribuez une licence et un numéro de téléphone si nécessaire.  

Lorsque vous avez une structure solide qui répond à vos besoins et un script qui guide efficacement les clients, procédez à la configuration des comptes [de ressources.](configure-onprem-ra.md)

## <a name="see-also"></a>Voir aussi

[Configurer des comptes de ressource](configure-onprem-ra.md)

[Activer l'enregistrement des invites personnalisées à l'aide de l'interface utilisateur de téléphonie](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Un standard Cloud automatique, qu’est-ce que c’est ?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[ Planifier une connectivité hybride entre Skype pour serveur d'entreprise et Microsoft 365 ou Office 365](plan-hybrid-connectivity.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](configure-hybrid-connectivity.md)

[Gérer les comptes de ressources dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
