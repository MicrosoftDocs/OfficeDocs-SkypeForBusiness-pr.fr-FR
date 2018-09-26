---
title: Planifier le service de messagerie vocale dans le nuage
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Cet article décrit les avantages, considérations relatives à la planification et configuration requise pour l’implémentation du Service de messagerie vocale de Microsoft dans le nuage. Pour plus d’informations sur la configuration de la messagerie vocale dans le nuage, voir Configuration de la messagerie vocale dans le nuage.
ms.openlocfilehash: e307ddcb5159e51ebe26e6a5bee10f9b2ee716e9
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "25030622"
---
# <a name="plan-cloud-voicemail-service"></a>Planifier le service de messagerie vocale dans le nuage

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a>Vue d’ensemble 

Cet article décrit les avantages, considérations relatives à la planification et configuration requise pour l’implémentation du service de messagerie vocale de Microsoft dans le nuage. Pour plus d’informations sur la configuration de la messagerie vocale dans le nuage, consultez [service de configurer la messagerie vocale dans le nuage](configure-cloud-voicemail.md).

Messagerie vocale dans le nuage prend la place de Exchange messagerie unifiée (MU) en fournissant des fonctionnalités de messagerie pour Skype pour les utilisateurs de voix entreprise 2019 disposant de boîtes aux lettres sur Exchange Server 2019 ou Exchange Online de voix. Messagerie vocale dans le nuage offre les avantages suivants pour vos utilisateurs en ligne et sur site :

- Fonctionnalités de répondeur automatique et de dépôt de messages de la messagerie vocale avec transcription vocales améliorées

- Accès à la messagerie vocale dans la boîte aux lettres Exchange de l’utilisateur à l’aide de la Skype pour les clients d’entreprise en ligne ou Outlook 

- La possibilité d’utiliser le portail Office 365 web pour gérer les options de la messagerie vocale

- Prise en charge des boîtes aux lettres Exchange sur site ou dans le cloud

- Tirer parti des messages d’accueil d’utilisateur existante à partir de la messagerie unifiée Exchange Online

Pour plus d’informations sur la comparaison des fonctionnalités, voir [planifier Skype pour Business Server et de migration d’Exchange Server](plan-um-migration.md). 

Skype pour Business Server 2019 continue à utiliser la messagerie unifiée Exchange pour les utilisateurs dont les boîtes aux lettres se trouvent sur des versions précédentes d’Exchange Server (2013, 2016).  Présentation de solution de messagerie vocale sera utilisée basées sur le serveur Exchange et Skype pour Business Server version est une part importante de la planification de migration vers soit Skype pour Business Server 2019 ou Exchange Server 2019. Pour plus d’informations sur la migration et d’interopérabilité, voir [planifier Skype pour Business Server et de migration d’Exchange Server](plan-um-migration.md). 

Avec la messagerie vocale dans le Cloud, les tâches d’administration sont simplifiées, car :

- Il n’est pas nécessaire de configurer le rôle de messagerie unifiée Exchange.
- Les tâches de configuration pour la messagerie vocale dans le nuage sont plus simples.
- Mises à jour des fonctionnalités de messagerie vocale sont remis directement dans le nuage, afin que vos utilisateurs ont toujours accès aux mises à jour avec une dépendance inférieure et fonctionnalités les plus récentes sur les mises à jour cumulatives (CUs).
- Vous avez le même ensemble de contrôles de locale et de boîtes aux lettres Exchange online. Pour plus d’informations sur ces contrôles, voir [configurer le système téléphonique de la messagerie vocale](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

Le diagramme suivant illustre la messagerie vocale dans le Cloud dans un déploiement hybride :


![Messagerie vocale SfB Cloud](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Les appels sans réponse sont traitées comme suit :  

1. Pour les utilisateurs hébergés dans Skype pour Business 2019 localement, les appels sans réponse sont transmis par la Skype locale pour Business Server vers le service de messagerie vocale dans le nuage en ligne. 
2. Le service traite la messagerie vocale, y compris la transcription.
3. Le service dépose ensuite la messagerie vocale dans la boîte aux lettres Exchange de l’utilisateur, si la boîte aux lettres est local ou en ligne.  
4. Les utilisateurs peuvent accéder en leur messagerie vocale à partir de leur Skype pour le client Outlook ou de l’entreprise.

## <a name="requirements"></a>Conditions requises

Les conditions suivantes supposent que vous avez déjà Skype pour Business Server déployé dans une topologie prise en charge.  Vos besoins dépendant de votre scénario :

- Si vous utilisez déjà la messagerie unifiée Exchange online et mise à niveau à Skype pour Business 2019, vous devrez modifier votre stratégie de messagerie vocale hébergée et vérifiez que les fournisseurs d’hébergement sont correctement. Pour plus d’informations, voir [configurer la messagerie vocale dans le Cloud service](configure-cloud-voicemail.md).

- Si vous utilisez la messagerie unifiée Exchange sur site ou si vous disposez d’une combinaison d’utilisateurs à l’aide de la messagerie unifiée Exchange online et sur site, vous devez modifiez votre stratégie de messagerie vocale hébergée et le fournisseur d’hébergement.  Pour plus d’informations, voir [configurer la messagerie vocale dans le Cloud service](configure-cloud-voicemail.md).

- Pour une nouvelle configuration de la messagerie vocale dans le nuage, suivez les étapes décrites dans le [service de configuration de la messagerie vocale dans le nuage](configure-cloud-voicemail.md).

Outre les conditions ci-dessus, la sous exigences doit être configuré pour se connecter au service de messagerie vocale de Microsoft dans le nuage :

- Connectivité hybride. Si vous avez déjà Skype pour Business Server est déployé, et que vous souhaitez activer la messagerie vocale dans le nuage pour vos utilisateurs sur site, vous devez vous assurer que vous disposez de connectivité hybride entre votre organisation locale et environnements en ligne. Il est parfois appelée une configuration de domaine fractionné. 

   Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Office 365](plan-hybrid-connectivity.md) et de [configurer la connectivité hybride entre Skype pour Business Server et Office 365](configure-hybrid-connectivity.md).

- Les utilisateurs doivent être activés pour Enterprise Voice et de la messagerie vocale hébergée dans Skype pour Business Server sur site.

- Un externe Exchange Web Services (EWS) URL et la découverte automatique doivent être le programme d’installation ou certaines fonctionnalités de messagerie vocale dans le nuage seront limitées.

-  Si vous avez un déploiement uniquement localement--qui est, uniquement Exchange et Skype pour les entreprises serveurs locaux, mais vous souhaitez profiter de la messagerie vocale dans le nuage, vous devez la licence de suite-PREM. 

##<a name="migration-and-interoperability"></a>Migration et interopérabilité

Si vous envisagez de déployer Skype pour Business Server 2019 et/ou 2019 du serveur Exchange, vous devez planifier votre migration avec soin pour en garantir continue du service de messagerie vocale. Tenez compte des points suivants :

- Exchange Server 2019 ne fournit plus de fonctionnalités de messagerie unifiée Exchange
- Skype pour Business Server 2019 intègre n’est plus avec la messagerie unifiée Exchange Online

Interopérabilité de la version et les topologies prises en charge pour la messagerie vocale dans le nuage sont répertoriés dans le tableau suivant. Pour la version preview, la messagerie vocale dans le nuage fonctionne uniquement avec Skype pour Business Server et Exchange Server 2019 ou Exchange Online.


|                               | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---------------------------    |:---------------------|:---------------------|:------------------|:---------------------- |
| Skype pour Business Server 2019 | Serveur de messagerie unifiée Exchange | Serveur de messagerie unifiée Exchange | Messagerie vocale dans le nuage | Messagerie vocale dans le nuage
Skype Entreprise Server 2015 | Serveur de messagerie unifiée Exchange | Serveur de messagerie unifiée Exchange |  | Messagerie vocale dans le nuage <br> Exchange Online MU * |
Lync Server 2013 <br>  | Serveur de messagerie unifiée Exchange | Serveur de messagerie unifiée Exchange | | Messagerie vocale dans le nuage <br> Exchange Online MU * |

\*Jusqu'à ce qu’obsolète.

Microsoft recommande les chemins de migration suivants :

-  Si vous mettez à niveau à Skype pour Business Server 2019, vous pouvez utiliser la messagerie unifiée Exchange dans Exchange Server 2013 ou 2016, mais vous devez mettre à niveau vers la messagerie vocale dans le nuage si vous utilisez Exchange Server 2019.

- Si vous mettez à niveau vers Exchange Server 2019 et que vous utilisez des versions antérieures de messagerie unifiée Exchange Server pour Skype pour Business Server de messagerie vocale, Microsoft recommande que vous mettre à niveau vers Skype pour Business Server 2019 avant la mise à niveau de la boîte aux lettres.  Dans le cas contraire, les fonctionnalités de messagerie vocale sera perdue. 


Pour plus d’informations sur la planification de votre migration, voir [planifier Skype pour Business Server et de migration d’Exchange Server](plan-um-migration.md).
