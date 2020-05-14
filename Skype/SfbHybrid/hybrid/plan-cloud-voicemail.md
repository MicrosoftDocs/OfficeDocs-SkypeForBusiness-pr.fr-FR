---
title: Planifier le service de messagerie vocale sur le Cloud pour les utilisateurs locaux | PBX Skype entreprise Server 2019
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
description: Cet article décrit les avantages, les considérations relatives à la planification et les conditions requises pour l’implémentation du service de messagerie vocale Microsoft Cloud. Pour plus d’informations sur la configuration de la messagerie vocale Cloud, consultez la rubrique Configuring Cloud vocaux.
ms.openlocfilehash: e07dfe76a60d107702891384458cf164a4744578
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221284"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planifier le service de messagerie vocale sur le Cloud pour les utilisateurs locaux

## <a name="overview"></a>Vue d’ensemble

Cet article décrit les avantages, les considérations relatives à la planification et les conditions requises pour l’implémentation du service de messagerie vocale Microsoft Cloud pour vos utilisateurs locaux. Pour plus d’informations sur la configuration de la messagerie vocale Cloud, consultez la rubrique [configurer le service de messagerie vocale Cloud](configure-cloud-voicemail.md).

La messagerie vocale Cloud prend la place de la messagerie unifiée Exchange pour fournir des fonctionnalités de messagerie vocale pour les utilisateurs de la messagerie vocale Skype entreprise 2019 qui possèdent des boîtes aux lettres sur Exchange Server 2019 ou Exchange Online. La messagerie vocale Cloud offre les avantages suivants pour vos utilisateurs locaux et en ligne :

- Fonctionnalité de réponse aux messages vocaux et de dépôt avec transcription de parole améliorée

- Accès à la messagerie vocale dans la boîte aux lettres Exchange de l’utilisateur à l’aide des clients Skype entreprise Online ou Outlook

- Possibilité d’utiliser le centre d’administration Microsoft 365 pour gérer les options de messagerie vocale

- Prise en charge des boîtes aux lettres Exchange sur site ou dans le Cloud

- Utilisation des messages d’accueil de la messagerie unifiée Exchange Online

Pour plus d’informations sur la comparaison des fonctionnalités, reportez-vous à la rubrique [plan for Skype for Business Server et Exchange Server Migration](plan-um-migration.md).

Skype entreprise Server 2019 continue d’utiliser la messagerie unifiée Exchange pour les utilisateurs dont les boîtes aux lettres se trouvent sur des versions antérieures d’Exchange Server (2013, 2016).  Comprendre quelle solution de messagerie vocale sera utilisée en fonction de la version d’Exchange Server et de Skype entreprise Server est un élément important de la planification de la migration vers Skype entreprise Server 2019 ou Exchange Server 2019. Pour plus d’informations sur la migration et l’interopérabilité, reportez-vous à la rubrique [plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Avec la messagerie vocale Cloud, vos tâches d’administration sont grandement simplifiées car :

- Il n’est pas nécessaire de configurer le rôle de messagerie unifiée Exchange.
- Les tâches de configuration de la messagerie vocale Cloud sont plus simples.
- Les mises à jour de la fonctionnalité de messagerie vocale sont fournies directement dans le Cloud, de sorte que vos utilisateurs ont toujours accès aux fonctionnalités et mises à jour les plus récentes avec une dépendance moindre sur les mises à jour cumulatives (CUs).
- Vous disposez du même ensemble de contrôles pour les boîtes aux lettres Exchange locales et en ligne. Pour plus d’informations sur ces contrôles, consultez la rubrique [configurer la messagerie vocale du système téléphonique](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

Le diagramme suivant montre la messagerie vocale dans le Cloud dans un déploiement hybride :

![Messagerie vocale Cloud SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Les appels sans réponse sont traités comme suit :  

1. Pour les utilisateurs hébergés dans Skype entreprise 2019 en local, les appels sans réponse sont envoyés par le serveur Skype entreprise sur site au service de messagerie vocale en ligne dans le Cloud.
2. Le service traite la messagerie vocale, y compris la transcription.
3. Le service dépose ensuite la messagerie vocale dans la boîte aux lettres Exchange de l’utilisateur, que la boîte aux lettres soit locale ou en ligne.  
4. Les utilisateurs peuvent accéder à leur messagerie vocale à partir de leur client Skype entreprise ou Outlook.

## <a name="requirements"></a>Configuration requise

Les conditions suivantes supposent que vous avez déjà déployé Skype entreprise Server dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Si vous utilisez déjà la messagerie unifiée Exchange en ligne et que vous effectuez une mise à niveau vers Skype entreprise 2019, vous devrez modifier votre stratégie de messagerie vocale hébergée et vérifier que vos fournisseurs d’hébergement sont correctement configurés. Pour plus d’informations, consultez la rubrique [configurer le service de messagerie vocale Cloud](configure-cloud-voicemail.md).

- Si vous utilisez la messagerie unifiée Exchange sur site, ou si vous avez un mélange d’utilisateurs utilisant la messagerie unifiée Exchange en ligne et sur site, vous devrez modifier la stratégie de messagerie vocale hébergée et le fournisseur d’hébergement.  Pour plus d’informations, consultez la rubrique [configurer le service de messagerie vocale Cloud](configure-cloud-voicemail.md).

- Pour une nouvelle configuration de la messagerie vocale sur le Cloud, suivez les étapes décrites dans [configurer le service de messagerie vocale](configure-cloud-voicemail.md)dans le Cloud.

En plus de la configuration requise ci-dessus, les conditions suivantes doivent être configurées pour se connecter au service de messagerie vocale Microsoft Cloud :

- Connectivité hybride. Si vous avez déjà déployé Skype entreprise Server et que vous souhaitez activer la messagerie vocale Cloud pour vos utilisateurs sur site, vous devez vous assurer que la connectivité hybride est configurée entre votre environnement local et en ligne. Il s’agit parfois d’une configuration de domaine fractionné.

   Pour plus d’informations, reportez-vous à [plan Hybrid Connectivity between Skype for Business Server et Microsoft 365 ou office 365](plan-hybrid-connectivity.md) et configuration de la [connectivité hybride entre Skype entreprise server et Office 365](configure-hybrid-connectivity.md).

- Les utilisateurs locaux doivent être activés pour voix entreprise et messagerie vocale hébergée dans Skype entreprise Server.

- Une URL de services Web Exchange externes (EWS) et une découverte automatique doivent être configurées ou certaines fonctionnalités de messagerie vocale Cloud seront limitées.

- Si vous disposez d’un déploiement local uniquement&#x2014;c’est-à-dire, uniquement des serveurs Exchange et Skype entreprise locaux&#x2014;mais que vous souhaitez tirer parti de la messagerie vocale Cloud, vous aurez besoin d’une licence de système téléphonique.

## <a name="migration-and-interoperability"></a>Migration et interopérabilité

Si vous envisagez de déployer Skype entreprise Server 2019 et/ou Exchange Server 2019, vous devez planifier soigneusement votre migration afin de garantir la continuité du service pour la messagerie vocale. Gardez les éléments suivants à l’esprit :

- Exchange Server 2019 ne fournit plus la fonctionnalité de messagerie unifiée Exchange
- Skype entreprise Server 2019 ne s’intègre plus à la messagerie unifiée Exchange Online

L’interopérabilité des versions et les topologies prises en charge pour la messagerie vocale Cloud sont répertoriées dans le tableau suivant, qui compare les versions de Skype entreprise Server auxquelles l’utilisateur peut être hébergé avec la version possible fournissant sa boîte aux lettres Exchange. Vous devez utiliser la messagerie vocale Cloud si vous voulez utiliser Skype entreprise 2019 avec Exchange Online ou Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype entreprise Server 2019 | Messagerie unifiée Exchange Server | Messagerie unifiée Exchange Server | Messagerie vocale cloud | Messagerie vocale cloud |
| Skype Entreprise Server 2015 | Messagerie unifiée Exchange Server | Messagerie unifiée Exchange Server | Messagerie vocale cloud | Messagerie vocale cloud |
| Lync Server 2013 <br>  | Messagerie unifiée Exchange Server | Messagerie unifiée Exchange Server | Non pris en charge | Messagerie vocale cloud |

Microsoft recommande les chemins de migration suivants :

- Si vous effectuez une mise à niveau vers Skype entreprise Server 2019, vous pouvez utiliser la messagerie unifiée Exchange dans Exchange Server 2013 ou 2016, mais vous devez effectuer une mise à niveau vers la messagerie vocale Cloud si vous utilisez Exchange Server 2019.
- Si vous effectuez une mise à niveau vers Exchange Server 2019 et que vous utilisez des versions précédentes de la messagerie UNIFIÉe Exchange Server pour la messagerie vocale Skype entreprise Server, Microsoft vous recommande d’effectuer une mise à niveau vers Skype entreprise Server 2019 avant la mise à niveau de la boîte aux lettres.  Dans le cas contraire, les fonctionnalités de messagerie vocale seront perdues.
- Si vous effectuez une mise à niveau vers Skype entreprise Server 2019 et que Skype entreprise Server 2015 est configuré pour la messagerie vocale Exchange Online, la messagerie vocale des utilisateurs migre automatiquement de la messagerie UNIFIÉe Exchange Online vers la messagerie vocale Cloud lorsque leur compte est déplacé vers Skype entreprise Server 2019. 

Pour plus d’informations sur la planification de la migration, reportez-vous à la rubrique [plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).
