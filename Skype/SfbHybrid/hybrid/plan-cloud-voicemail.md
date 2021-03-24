---
title: Planifier le service de messagerie vocale cloud pour les utilisateurs locaux| PBX Skype Entreprise Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Cet article décrit les avantages, les considérations relatives à la planification et les conditions requises pour l’implémentation du service de messagerie vocale Microsoft Cloud. Pour plus d’informations sur la configuration de la messagerie vocale cloud, voir Configuring Cloud Voicemail.
ms.openlocfilehash: 4ae274f33d2b7d52c486cd9031d01bc3a532a6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110280"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planifier le service de messagerie vocale cloud pour les utilisateurs locaux

## <a name="overview"></a>Vue d'ensemble

Cet article décrit les avantages, les considérations relatives à la planification et les conditions requises pour l’implémentation du service de messagerie vocale Microsoft Cloud pour vos utilisateurs locaux. Pour plus d’informations sur la configuration de la messagerie vocale cloud, voir Configurer le [service de messagerie vocale cloud.](configure-cloud-voicemail.md)

La messagerie vocale cloud prend la place de la messagerie unifiée Exchange en fournissant des fonctionnalités de messagerie vocale pour les utilisateurs de la messagerie vocale Skype Entreprise 2019 qui ont des boîtes aux lettres sur Exchange Server 2019 ou Exchange Online. La messagerie vocale cloud offre les avantages suivants pour vos utilisateurs locaux et en ligne :

- Fonctionnalité de répondeur vocal et de dépôt avec transcription vocale améliorée

- Accès à la messagerie vocale dans la boîte aux lettres Exchange de l’utilisateur à l’aide des clients Skype Entreprise Online ou Outlook

- Possibilité d’utiliser le Centre d’administration Microsoft 365 pour gérer les options de messagerie vocale

- Prise en charge des boîtes aux lettres Exchange en local ou dans le cloud

- Exploitation des messages d’accueil des utilisateurs existants à partir de la messagerie unifiée Exchange Online

> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi les utilisateurs ne pourront plus accéder à la messagerie vocale dans leur boîte aux lettres Exchange via le client Skype Entreprise Online.

Pour plus d’informations sur la comparaison des fonctionnalités, voir [Plan for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)

Skype Entreprise Server 2019 continue d’utiliser la messagerie un peu plus récente pour les utilisateurs dont les boîtes aux lettres utilisent des versions antérieures de Exchange Server (2013, 2016).  Comprendre la solution de messagerie vocale à utiliser en fonction de la version Exchange Server et Skype Entreprise Server est une partie importante de la planification de la migration vers Skype Entreprise Server 2019 ou Exchange Server 2019. Pour plus d’informations sur la migration et l’interopérabilité, voir [Plan for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)

Avec la messagerie vocale cloud, vos tâches d’administration sont considérablement simplifiées pour les raisons suivantes :

- Il n’est pas nécessaire de configurer le rôle de la um Exchange.
- Les tâches de configuration de la messagerie vocale cloud sont plus simples.
- Les mises à jour des fonctionnalités de messagerie vocale sont directement mises à jour dans le cloud. Vos utilisateurs ont donc toujours accès aux dernières fonctionnalités et mises à jour avec moins de dépendance sur les mises à jour cumulatives.
- Vous avez le même ensemble de contrôles pour les boîtes aux lettres Exchange en ligne et sur site. Pour plus d’informations sur ces contrôles, voir [Configurer la messagerie vocale du système téléphonique.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

Le diagramme suivant illustre la messagerie vocale cloud dans un déploiement hybride :

![Messagerie vocale cloud SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Les appels sans réponse sont gérés comme suit :  

1. Pour les utilisateurs de Skype Entreprise 2019 en local, les appels sans réponse sont envoyés par Skype Entreprise Server local au service de messagerie vocale cloud en ligne.
2. Le service traite la messagerie vocale, y compris la transcription.
3. Le service dépose ensuite la messagerie vocale dans la boîte aux lettres Exchange de l’utilisateur, que la boîte aux lettres soit en local ou en ligne.  
4. Les utilisateurs peuvent accéder à leur messagerie vocale à partir de leur client Skype Entreprise ou Outlook.

## <a name="requirements"></a>Configuration requise

Les conditions suivantes supposent que Skype Entreprise Server est déjà déployé dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Si vous utilisez déjà la messagerie un utilisateur exchange en ligne et que vous faites une mise à niveau vers Skype Entreprise 2019, vous devez modifier votre stratégie de messagerie vocale hébergée et vérifier que vos fournisseurs d’hébergement sont correctement définies. Pour plus d’informations, [voir Configurer le service de messagerie vocale cloud.](configure-cloud-voicemail.md)

- Si vous utilisez la messagerie un utilisateur Exchange en local ou si vous avez un mélange d’utilisateurs utilisant la messagerie un3e utilisateur Exchange en ligne et en local, vous devez modifier votre stratégie de messagerie vocale hébergée et votre fournisseur d’hébergement.  Pour plus d’informations, [voir Configurer le service de messagerie vocale cloud.](configure-cloud-voicemail.md)

- Pour une nouvelle configuration de la messagerie vocale cloud, suivez les étapes décrites dans Configurer le [service de messagerie vocale cloud.](configure-cloud-voicemail.md)

Outre la configuration requise ci-dessus, les conditions ci-dessous doivent être configurées pour se connecter au service de messagerie vocale Microsoft Cloud :

- Connectivité hybride. Si Skype Entreprise Server est déjà déployé et que vous souhaitez activer la messagerie vocale cloud pour vos utilisateurs locaux, vous devez vous assurer que la connectivité hybride est définie entre vos environnements locaux et en ligne. Il s’agit parfois d’une configuration de domaine fractionnement.

   Pour plus d’informations, voir Planifier la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) et configurer la connectivité hybride entre Skype Entreprise Server et [Office 365.](configure-hybrid-connectivity.md)

- Les utilisateurs locaux doivent être activés pour Voix Entreprise messagerie vocale hébergée dans Skype Entreprise Server.

- Une URL des services web Exchange externes (EWS) et la découverte automatique doivent être définies, sinon certaines fonctionnalités de messagerie vocale cloud seront limitées.

- Si vous avez un serveur Exchange local, configurer la messagerie vocale cloud à l’aide des étapes de la procédure de mise en place de la messagerie vocale cloud pour les utilisateurs [Exchange Server boîte aux lettres.](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)

## <a name="migration-and-interoperability"></a>Migration et interopérabilité

Si vous envisagez de déployer Skype Entreprise Server 2019 et/ou Exchange Server 2019, vous devez planifier votre migration avec soin pour garantir un service continu pour la messagerie vocale. Gardez les éléments suivants à l’esprit :

- Exchange Server 2019 ne fournit plus la fonctionnalité de la um Exchange
- Skype Entreprise Server 2019 ne s’intègre plus à la messagerie un utilisateur Exchange Online

L’interopérabilité de version et les topologies pris en charge pour la messagerie vocale cloud sont répertoriés dans le tableau suivant, qui compare les versions de Skype Entreprise Server sur lesquelles l’utilisateur peut être reçu avec la version possible fournissant sa boîte aux lettres Exchange. Vous devez utiliser la messagerie vocale cloud si vous souhaitez utiliser Skype Entreprise 2019 avec Exchange Online ou Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype Entreprise Server 2019 | Exchange Server UM | Exchange Server UM | Messagerie vocale cloud | Messagerie vocale cloud |
| Skype Entreprise Server 2015 | Exchange Server UM | Exchange Server UM | Non pris en charge | Messagerie vocale cloud |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | Non pris en charge | Messagerie vocale cloud |

Microsoft recommande les chemins de migration suivants :

- Si vous faites une mise à niveau vers Skype Entreprise Server 2019, vous pouvez utiliser la messagerie un Exchange Server Exchange dans Exchange Server 2013 ou 2016, mais vous devez la mettre à niveau vers la messagerie vocale cloud si vous utilisez Exchange Server 2019.
- Si vous êtes en cours de mise à niveau vers Exchange Server 2019 et que vous utilisez des versions précédentes de la messagerie vocale Exchange Server um for Skype for Business Server, Microsoft vous recommande de mettre à niveau vers Skype Entreprise Server 2019 avant la mise à niveau de la boîte aux lettres.  Dans le cas contraire, les fonctionnalités de messagerie vocale seront perdues.
- Si vous effectuez une mise à niveau vers Skype Entreprise Server 2019 et que Skype Entreprise Server 2015 est configuré pour la messagerie vocale avec la messagerie unée Exchange Online, la messagerie vocale des utilisateurs migre automatiquement de la messagerie unée Exchange Online vers la messagerie vocale cloud lorsque leur compte est déplacé vers Skype Entreprise Server 2019. 

Pour plus d’informations sur la planification de votre migration, voir [Plan for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)