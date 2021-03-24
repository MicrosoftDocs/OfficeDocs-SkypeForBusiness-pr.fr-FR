---
title: Planifier un attendant automatique cloud
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
description: Vue d’ensemble de l’utilisation d’un attendant automatique cloud avec Skype Entreprise Server 2019
ms.openlocfilehash: b144576b3e572137a512881f4bdcd1ab0e06d0ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110350"
---
# <a name="plan-cloud-auto-attendants"></a>Planifier les standards automatiques cloud

Le attendant automatique utilisé avec la messagerie unifiée Exchange (Exchange Server 2013 ou Exchange Server 2016) n’est plus disponible dans Exchange Server 2019 ou Exchange Online. Si votre implémentation de Skype Entreprise Server 2019 s’intègre à l’une de ces versions d’Exchange, vous devez utiliser les fonctionnalités Cloud Voice en ligne associées au système téléphonique. Pour plus d’informations sur le déplacement des services de messagerie unée Exchange sur Exchange server 2013 et 2016 vers le cloud, voir Planifier la migration de Skype Entreprise Server et de [Exchange Server.](plan-um-migration.md)

Cela signifie intrinsèquement que vous aurez une implémentation hybride de Skype Entreprise Server 2019 si vous souhaitez utiliser des fonctionnalités de messagerie unifiée telles que les attendants automatiques. Pour plus d’informations, voir Configurer la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md)

Un attendant automatique est un service cloud qui accepte les appels des clients et lit des salutations, leur fournit des options de menu et interagit avec les appelants à l’aide de la reconnaissance vocale ou du pavé de numérotation pour router leurs appels vers la bonne destination. Un compte de ressource *(voir* Configurer les comptes de [ressources)](configure-onprem-ra.md)est affecté à chaque attendant automatique sur votre système Skype Entreprise Server 2019 qui sera lié directement à un service de gestion automatique dans le Centre d’administration Microsoft Teams. Pour [plus d’informations sur les attendants automatiques](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) et les options et fonctionnalités disponibles pour les attendants automatiques, consultez la liste des attendants automatiques cloud.

> [!NOTE]
> Vous pouvez affecter plusieurs numéros de service Microsoft, des numéros de routage direct ou des numéros hybrides à un service de sécurité automatique.

Un appel entrant vers un service de attendant automatique cloud peut prendre l’un des chemins d’accès indiqués ci-après :

![Diagramme pour les attendants automatiques](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype Entreprise Server 2019
2. Via un contrôleur [de frontière de session](/MicrosoftTeams/direct-routing-border-controllers.md) et un [routage direct](/MicrosoftTeams/direct-routing-plan.md)
3. Via un numéro en ligne dans Microsoft 365 ou Office 365.

Consulter également :

- [Configurer un standard automatique dans le cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Réponse et routage automatique d’appels entrants](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Configuration requise

Les conditions suivantes supposent que Skype Entreprise Server 2019 est déjà déployé dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Si vous utilisez déjà la um Exchange en ligne ou en local et que vous faites une mise à niveau vers Skype Entreprise 2019, vous devrez capturer la structure de vos attendants automatiques et les re-créer dans le cloud à l’aide des normes automatiques cloud. Pour plus d’informations, voir [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Pour une nouvelle configuration des attendants automatiques cloud, suivez les étapes décrites dans [Configurer les comptes de ressources.](configure-onprem-ra.md)

Outre la configuration requise ci-dessus, les conditions ci-dessous doivent être configurées pour se connecter au service de service de attendant automatique Microsoft Cloud :

- Connectivité hybride. Si Skype Entreprise Server est déjà déployé et que vous souhaitez activer le service de gestion automatique cloud pour vos utilisateurs locaux, vous devez vous assurer que la connectivité hybride est définie entre vos environnements locaux et en ligne. Il s’agit parfois d’une configuration de domaine fractionnement.

   Pour plus d’informations, voir Planifier la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) et configurer la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md)

- Si vous affectez un numéro de téléphone à votre attendant automatique, vous aurez besoin d’une licence [Office 365 Entreprise E5.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Créez un compte de ressource [](configure-onprem-ra.md) [en ligne](/MicrosoftTeams/manage-resource-accounts.md) ou local pour chaque numéro de téléphone et attribuez des numéros de téléphone et des licences. 

## <a name="migration-and-interoperability"></a>Migration et interopérabilité

Si vous envisagez de déployer Skype Entreprise Server 2019 et/ou Exchange Server 2019, vous devez planifier votre migration avec soin pour assurer une prise en charge continue des serveurs automatiques. Gardez les éléments suivants à l’esprit :

- Exchange Server 2019 ne fournit plus la fonctionnalité de la um Exchange
- La messagerie unifiée Exchange est en mode retrait
- Skype Entreprise Server 2019 ne s’intègre plus à la messagerie un utilisateur Exchange Online

Les serveurs automatiques cloud peuvent être configurés avec Skype Entreprise Server 2019, 2015 et 2013.

Microsoft recommande les chemins de migration suivants :

- Si vous êtes en cours de mise à niveau vers Skype Entreprise Server 2019, vous pouvez utiliser la messagerie un Exchange Server Exchange dans Exchange Server 2013 ou 2016, mais vous devez la mettre à niveau vers le service de gestion automatique cloud si vous utilisez Exchange Server 2019.

- Si vous êtes en cours de mise à niveau vers Exchange Server 2019 et que vous utilisez des versions précédentes de la messagerie vocale Exchange Server um for Skype for Business Server, Microsoft vous recommande de mettre à niveau vers Skype Entreprise Server 2019 avant la mise à niveau de la boîte aux lettres.  Dans le cas contraire, les fonctionnalités de messagerie vocale seront perdues.

Pour plus d’informations sur la planification de votre migration, voir [Plan for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migration d’un système de attendant automatique de la um Exchange précédemment implémenté

Pour l’instant, nous ne allons pas prendre en charge la migration automatisée vers le cloud d’un système de surveillance automatique de la um créé dans Exchange 2013 ou 2016. Pour créer manuellement un système de attendant automatique, vous devez :

1. Utilisez les commandes PowerShell de l’administrateur Exchange pour passer en revue la structure de l’ancien système de attendant automatique, y compris les attendants automatiques imbrique et les files d’attente d’appels.  
2. Créez des copies de scripts de texte par reconnaissance vocale ou des messages enregistrés associés à chaque nœud de attendant automatique de messagerie unée.
3. Créez des points de terminaison locaux pour chaque nœud de attendant automatique, y compris l’attribution de numéros de téléphone de test et de licences aux objets. Notez que vous avez désormais la possibilité d’attribuer des licences de numéros de téléphone locaux utilisés par des services en ligne tels que le système téléphonique.
4. Implémenter un nouveau service de service de transport automatique cloud avec Microsoft Teams et le système téléphonique. Pour [plus d’informations sur l’implémentation,](configure-onprem-ra.md) voir Configurer les comptes de ressources. Comme vous le faites, téléchargez les scripts de texte par reconnaissance vocale ou les messages enregistrés associés à chaque nœud de attendant automatique de messagerie unée.
5. Testez les fonctionnalités du service de attendant automatique cloud.
6. Réaffectez le numéro de téléphone affecté à l’ancien attendant automatique de la um Exchange au nouveau numéro de téléphone principal cloud.

Pour plus [d’informations](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) sur ces étapes, voir Déplacement d’un service de transport automatique ou d’une file d’attente d’appels de la um Exchange vers le système téléphonique.

Lorsque vous avez une structure solide qui répond à vos besoins et un script qui guide efficacement les clients, procédez à la configuration des comptes [de ressources.](configure-onprem-ra.md)

> [!CAUTION]
> Comme mentionné dans [la KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)il est déconseillé de déplacer des serveurs exécutant Server 2019 vers des serveurs exécutant Server 2019 pour les serveurs de messagerie unie créés dans Server 2015. Pour l’instant, vous devez les conserver sur un pool Skype Entreprise Server 2015 en mode coexistence.

## <a name="see-also"></a>Voir aussi

[Planifier la migration pour Skype Entreprise Server et Exchange Server](plan-um-migration.md)

[Configurer des comptes de ressource](configure-onprem-ra.md)

[Activer l'enregistrement des invites personnalisées à l'aide de l'interface utilisateur de téléphonie](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Un standard Cloud automatique, qu’est-ce que c’est ?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurer un standard automatique dans le cloud](/microsoftteams/create-a-phone-system-auto-attendant)

Um Exchange : [répondre et router automatiquement les appels entrants](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[ Planifier une connectivité hybride entre Skype pour serveur d'entreprise et Microsoft 365 ou Office 365](plan-hybrid-connectivity.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](configure-hybrid-connectivity.md)

[KB4480742 : les appels à l’accès abonné ou au attendant automatique échouent avec une occupé rapide et une erreur « 500 Serveur interne » après le déplacement d’objets contact vers Skype Entreprise Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)