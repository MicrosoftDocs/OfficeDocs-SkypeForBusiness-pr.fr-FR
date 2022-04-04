---
title: Planifier Messagerie vocale infonuagique service pour les utilisateurs locaux| PBX Skype Entreprise Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Cet article décrit les avantages, les considérations relatives à la planification et les conditions requises pour l’Messagerie vocale infonuagique Microsoft service. Pour plus d’informations sur la configuration Messagerie vocale infonuagique, voir Configuring Messagerie vocale infonuagique.
ms.openlocfilehash: 4aefe6485dd4eee8321ea56bf12d68799a31de45
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563733"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planifier Messagerie vocale infonuagique service pour les utilisateurs locaux

## <a name="overview"></a>Présentation

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cet article décrit les avantages, les considérations relatives à la planification et les conditions requises pour implémenter le service Messagerie vocale infonuagique Microsoft pour vos utilisateurs locaux. Pour plus d’informations sur la configuration Messagerie vocale infonuagique, voir [Configure Messagerie vocale infonuagique service](configure-cloud-voicemail.md).

Messagerie vocale infonuagique prend la place de la messagerie unifiée Exchange pour fournir des fonctionnalités de messagerie vocale aux utilisateurs vocaux Skype Entreprise 2019 qui ont des boîtes aux lettres sur Exchange Server 2019 ou Exchange Online. Messagerie vocale infonuagique offre les avantages suivants pour vos utilisateurs locaux et en ligne :

- Fonctionnalité de répondeur vocal et de dépôt avec transcription vocale améliorée

- Accès à la messagerie vocale dans la boîte aux lettres Exchange’utilisateur à l’aide des clients Skype Entreprise Online ou Outlook

- Possibilité d’utiliser le Centre d'administration Microsoft 365 pour gérer les options de messagerie vocale

- Prise en charge Exchange boîtes aux lettres en local ou dans le cloud

- Exploitation des messages d’accueil des utilisateurs Exchange Online messagerie unifiée

> [!Important]
> Skype Entreprise Online a été retiré le 31 juillet 2021. Les utilisateurs ne peuvent plus accéder à la messagerie vocale dans leur boîte Exchange aux lettres via le client Skype Entreprise Online.

Pour plus d’informations sur la comparaison des fonctionnalités, voir [Plan for Skype Entreprise Server and Exchange Server migration](plan-um-migration.md).

Skype Entreprise Server 2019 continue d’utiliser la messagerie un Exchange pour les utilisateurs dont les boîtes aux lettres utilisent des versions antérieures de Exchange Server (2013, 2016).  Comprendre quelle solution de messagerie vocale sera utilisée en fonction de la version Exchange Server et Skype Entreprise Server est une partie importante de la planification de la migration vers Skype Entreprise Server 2019 ou Exchange Server 2019. Pour plus d’informations sur la migration et l’interopérabilité, voir [Plan for Skype Entreprise Server and Exchange Server migration](plan-um-migration.md).

Avec Messagerie vocale infonuagique, vos tâches d’administration sont considérablement simplifiées pour les raisons suivantes :

- Il n’est pas nécessaire de configurer le rôle de Exchange de la personne.
- Les tâches de configuration des Messagerie vocale infonuagique sont plus simples.
- Les mises à jour des fonctionnalités de messagerie vocale sont directement mises à jour dans le cloud. Vos utilisateurs ont donc toujours accès aux dernières fonctionnalités et mises à jour avec moins de dépendance sur les mises à jour cumulatives.
- Vous avez le même ensemble de contrôles pour les boîtes aux lettres de boîtes aux lettres Exchange en ligne et en local. Pour plus d’informations sur ces contrôles, voir [Configurer Système téléphonique messagerie vocale](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

Le diagramme suivant illustre les Messagerie vocale infonuagique dans un déploiement hybride :

![SfB Messagerie vocale infonuagique.](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Les appels sans réponse sont gérés comme suit :  

1. Pour les utilisateurs Skype Entreprise 2019 en local, les appels sans réponse sont envoyés par l’Skype Entreprise Server local au service d’Messagerie vocale infonuagique en ligne.
2. Le service traite la messagerie vocale, y compris la transcription.
3. Le service dépose ensuite la messagerie vocale dans la boîte Exchange de l’utilisateur, que la boîte aux lettres soit en local ou en ligne.  
4. Les utilisateurs peuvent accéder à leur messagerie vocale à partir de leur client Skype Entreprise ou Outlook client.

## <a name="requirements"></a>Conditions requises

Les conditions suivantes supposent que vous avez déjà déployé Skype Entreprise Server dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Si vous utilisez déjà la messagerie un Exchange en ligne et que vous faites une mise à niveau vers Skype Entreprise 2019, vous devez modifier votre stratégie de messagerie vocale hébergée et vérifier que vos fournisseurs d’hébergement sont correctement définies. Pour plus d’informations, [voir Configure Messagerie vocale infonuagique service](configure-cloud-voicemail.md).

- Si vous utilisez la messagerie un Exchange en local ou si vous avez un mélange d’utilisateurs utilisant la messagerie un Exchange en ligne et en local, vous devez modifier votre stratégie de messagerie vocale hébergée et votre fournisseur d’hébergement.  Pour plus d’informations, [voir Configure Messagerie vocale infonuagique service](configure-cloud-voicemail.md).

- Pour une nouvelle configuration de Messagerie vocale infonuagique, suivez les étapes décrites dans [Configure Messagerie vocale infonuagique service](configure-cloud-voicemail.md).

Outre la configuration requise ci-dessus, les conditions suivantes doivent être configurées pour se connecter au service Messagerie vocale infonuagique Microsoft:

- Connectivité hybride. Si vous avez déjà déployé Skype Entreprise Server et que vous souhaitez activer Messagerie vocale infonuagique pour vos utilisateurs locaux, vous devez vous assurer que la connectivité hybride est définie entre vos environnements locaux et en ligne. Il s’agit parfois d’une configuration de domaine fractionnement.

   Pour plus d’informations, voir [Plan hybrid connectivity between Skype Entreprise Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype Entreprise Server and Office 365](configure-hybrid-connectivity.md).

- Les utilisateurs locaux doivent être activés pour Voix Entreprise messagerie vocale hébergée dans Skype Entreprise Server.

- Une URL Exchange Web Services web externes (EWS) et la découverte automatique doivent être définies, sinon certaines fonctionnalités Messagerie vocale infonuagique seront limitées.

- Si vous avez un serveur Exchange local, Messagerie vocale infonuagique à l’aide des étapes de la procédure Set [up Messagerie vocale infonuagique for Exchange Server Mailbox Users](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).

## <a name="migration-and-interoperability"></a>Migration et interopérabilité

Si vous envisagez de déployer Skype Entreprise Server 2019 et/ou Exchange Server 2019, vous devez planifier votre migration avec soin pour garantir un service continu pour la messagerie vocale. Gardez les éléments suivants à l’esprit :

- Exchange Server 2019 ne fournit plus la fonctionnalité de Exchange de la Exchange de l’équipe
- Skype Entreprise Server 2019 ne s’intègre plus à la Exchange Online de l’équipe

L’interopérabilité des versions et les topologies prise en charge pour Messagerie vocale infonuagique sont répertoriées dans le tableau suivant, qui compare les versions Skype Entreprise Server sur lesquelles l’utilisateur peut être homed et la version possible fournissant sa boîte aux lettres Exchange. Vous devez utiliser Messagerie vocale infonuagique si vous souhaitez utiliser Skype Entreprise 2019 avec Exchange Online ou Exchange Server 2019.

| Skype/Lync | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype Entreprise Server 2019 | Exchange Server um | Exchange Server um | Messagerie vocale cloud | Messagerie vocale cloud |
| Skype Entreprise Server 2015 | Exchange Server um | Exchange Server um | Non pris en charge | Messagerie vocale cloud |
| Lync Server 2013 <br>  | Exchange Server um | Exchange Server um | Non pris en charge | Messagerie vocale cloud |

Microsoft recommande les chemins de migration suivants :

- Si vous faites une mise à niveau vers Skype Entreprise Server 2019, vous pouvez utiliser la Exchange um dans Exchange Server 2013 ou 2016, mais vous devez mettre à niveau vers Messagerie vocale infonuagique si vous utilisez Exchange Server 2019.
- Si vous êtes en cours de mise à niveau vers Exchange Server 2019 et que vous utilisez des versions antérieures de la messagerie un Exchange Server pour la messagerie vocale Skype Entreprise Server, Microsoft vous recommande de mettre à niveau vers Skype Entreprise Server 2019 avant la mise à niveau de boîte aux lettres.  Dans le cas contraire, les fonctionnalités de messagerie vocale seront perdues.
- Si vous effectuez une mise à niveau vers Skype Entreprise Server 2019 et que Skype Entreprise Server 2015 est configuré pour la messagerie vocale avec la messagerie un Exchange Online, la messagerie vocale des utilisateurs migre automatiquement de la messagerie un Exchange Online vers la messagerie un Exchange Online Messagerie vocale infonuagique lorsque son compte est déplacé vers Skype Entreprise Server 2019. 

Pour plus d’informations sur la planification de votre migration, voir [Plan for Skype Entreprise Server and Exchange Server migration](plan-um-migration.md).