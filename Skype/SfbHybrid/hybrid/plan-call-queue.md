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
ms.localizationpriority: medium
ms.collection: ''
description: Vue d’ensemble de l’utilisation d’un standard automatique cloud avec Skype Entreprise Server 2019.
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615420"
---
# <a name="plan-cloud-call-queues"></a>Planifier les files d’attente d’appels cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

La file d’attente d’appels cloud est un service qui accepte les appels des clients, lit un message d’accueil, puis place ces appels dans une file d’attente lors de la recherche d’une liste préconfigurée d’agents pour répondre à ces appels. Vous pouvez définir l’ensemble d’agents dans des listes de distribution ou des groupes de sécurité à extension messagerie. Votre organisation peut avoir une ou plusieurs files d’attente d’appels. Les files d’attente d’appels sont généralement utilisées en combinaison avec les standards automatiques.

En outre, les files d’attente d’appels cloud peuvent fournir :

- Musique pendant que les appelants attendent en attente
- Paramètres personnalisés pour la taille maximale de la file d’attente d’appels, le délai d’expiration et les options de gestion des appels

Chaque file d’attente d’appels se voit attribuer un **compte de ressource** (voir [Configurer les comptes de ressources](configure-onprem-ra.md)) sur votre système Skype Entreprise Server 2019 qui sera lié directement à une file d’attente d’appels dans le Centre d’administration Microsoft Teams. Pour plus d’informations sur les files d’attente d’appels et les options et fonctionnalités qui existent pour les files d’attente d’appels, consultez [Créer une file d’attente d’appels cloud](/MicrosoftTeams/create-a-phone-system-call-queue) .

> [!NOTE]
> Vous pouvez affecter plusieurs numéros de téléphone à une file d’attente d’appels, mais il doit s’agir de numéros de service Microsoft, de numéros de routage direct ou de numéros hybrides.

## <a name="requirements"></a>Conditions requises

Les exigences suivantes supposent que vous avez déjà Skype Entreprise Server 2019 déployé dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Pour une nouvelle configuration des files d’attente d’appels cloud, suivez les étapes décrites dans [Configurer les comptes de ressources](configure-onprem-ra.md). Vous devrez créer des comptes de ressources en ligne ou dans Skype Entreprise Server 2019, et vous devrez peut-être également associer un numéro de téléphone à la file d’attente des appels.

Outre les exigences ci-dessus, les exigences ci-dessous doivent être configurées pour se connecter au service de file d’attente d’appels Microsoft Cloud :

- Connectivité hybride. Si vous avez déjà Skype Entreprise Server déployé et que vous souhaitez activer les files d’attente d’appels cloud pour vos utilisateurs locaux, vous devez vous assurer que vous disposez d’une connectivité hybride configurée entre vos environnements locaux et en ligne. Il s’agit parfois d’une configuration de domaine fractionné.

   Pour plus d’informations, consultez [Planifier la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) et [configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](configure-hybrid-connectivity.md).

- Si vous attribuez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence **de compte de ressources Téléphonie Microsoft Teams** gratuite. Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation et vous permet de créer des fonctionnalités de standard automatique et de file d’attente d’appels.

- Créez un [compte de ressource](configure-onprem-ra.md) local pour chaque file d’attente d’appels et attribuez une licence et un numéro de téléphone si nécessaire.  

Lorsque vous disposez d’une structure solide qui répond à vos besoins et d’un script qui guide efficacement les clients, passez à  [Configurer les comptes de ressources](configure-onprem-ra.md).

## <a name="see-also"></a>Voir aussi

[Configurer des comptes de ressource](configure-onprem-ra.md)

[Activer l'enregistrement des invites personnalisées à l'aide de l'interface utilisateur de téléphonie](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Un standard Cloud automatique, qu’est-ce que c’est ?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurer un standard automatique dans le cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[ Planifier une connectivité hybride entre Skype pour serveur d'entreprise et Microsoft 365 ou Office 365](plan-hybrid-connectivity.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](configure-hybrid-connectivity.md)

[Gérer les comptes de ressources dans Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)