---
title: Déployer le pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une des premières étapes requises pour la migration vers Skype pour Business Server 2019 est de déployer un pool pilote. Le pool pilote est où vous testez la coexistence de Skype pour Business Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu'à ce que vous avez déplacé tous les utilisateurs et les pools à Skype pour Business Server 2019.
ms.openlocfilehash: 26f391a485c991aa3575498b98b181f1b5ac761c
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026048"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Déployer Skype pour le pool pilote Business Server 2019

Une des premières étapes requises pour la migration vers Skype pour Business Server 2019 est de déployer un pool pilote. Le pool pilote est où vous testez la coexistence de Skype pour Business Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu'à ce que vous avez déplacé tous les utilisateurs et les pools à Skype pour Business Server 2019. 
  
Lorsque vous déployez un pool pilote, vous utilisez l’Assistant définir un nouveau Pool frontal. Vous devez déployer les mêmes fonctionnalités et les charges de travail dans votre Skype pour le pool pilote Business Server 2019 que vous avez dans votre pool hérité. Si vous avez déployé le serveur d’archivage, le serveur de surveillance ou System Center Operations Manager pour l’archivage ou la surveillance de votre environnement hérité et que vous souhaitez continuer l’archivage ou la surveillance pendant la migration, vous devez également déployer ces fonctionnalités dans votre environnement pilote. La version que vous avez déployé pour archiver ou surveiller votre hérité environnement ne peut capturer les données dans votre Skype pour environnement Business Server 2019. 
  
> [!NOTE]
> La procédure suivante décrit les fonctionnalités et les paramètres que vous devez prendre en compte dans le cadre de votre processus de déploiement du pool pilote global. Cette section met en évidence uniquement les points clés que vous devez prendre en compte dans le cadre de votre déploiement du pool pilote. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Pour déployer un Skype pour le pool pilote Business Server 2019

1. Ouvrez une session l’ordinateur où le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.
    
2. Développez l’arborescence jusqu'à ce que vous atteigniez **Skype pour Business Server 2019** > **pools frontaux Enterprise Edition**.
    
3. Avec le bouton droit de **pools frontaux Enterprise Edition** et sélectionnez **Nouveau Pool frontal**.
  
4. Entrez le nom de domaine complet (FQDN) du pool. Lorsque vous définissez votre pool pilote, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition server. Skype pour Business Server 2019 ne nécessite pas que les fonctionnalités de votre pool pilote correspond à ce qui a été déployé dans votre pool hérité.
    
    > [!CAUTION]
    > Le pool ou le serveur de nom de domaine complet que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool hérité actuellement déployé ou tout autre serveur actuellement déployé. 
  
5. Dans la page **Sélectionner les fonctionnalités** , activez les cases à cocher pour les fonctionnalités que vous voulez sur ce pool frontal. Par exemple, si vous déployez uniquement la messagerie instantanée (MI) et les fonctionnalités de présence, vous, sélectionnez la case à cocher de conférence pour autoriser la conversation par messagerie instantanée, mais vous ne sélectionnez pas de conférence rendez-vous (PSTN), Enterprise Voice, ou vérifier le contrôle d’admission des appels d’appel zones, car ils représentent voice, les fonctionnalités de conférence vidéo et de collaboration. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Dans la page **des rôles serveur colocalisés Select** , nous vous recommandons de choisir de colocaliser le serveur de médiation dans Skype pour Business Server 2019. Lors de la fusion d’une topologie héritée avec Skype pour Business Server 2019, nous avons besoin que vous colocalisez tout d’abord le serveur de médiation hérité. Après avoir fusionner les topologies et configuré le Skype pour le serveur de médiation 2019 Business Server, vous pouvez décider s’il faut conserver le serveur de médiation colocalisé ou remplacez-le par un serveur autonome lorsque vous déplacez le rôle de serveur de médiation vers Skype pour Business Server 2019 plus loin dans le processus de déploiement. 
   
7. Dans la page **associer des rôles de serveur à ce pool frontal** , au cours du déploiement du pool pilote, *ne mais pas* choisir l’option **Activer un pool de serveurs Edge devant être utilisé par le composant de support de ce pool frontal** . Il s’agit d’une fonctionnalité que vous activez et mettre en ligne dans une phase ultérieure de la migration. Maintenir ce paramètre est désactivé pour l’instant. 
  
8. Dans la page **Sélectionner un serveur Office Web Apps Server** , cliquez sur **Nouveau**et spécifiez le nom de domaine complet du serveur d’applications.
  
9. Dans la page **définir le magasin SQL Server d’archivage** , lors de la définition du magasin SQL Server pour les deux Skype pour Business Server archivage et la surveillance, sélectionnez l’instance de SQL Server créée précédemment pour Skype pour Business Server 2019. 
  
10. Pour publier votre topologie, cliquez sur le nœud **Skype pour Business Server** , puis cliquez sur **Publier la topologie**.
  
11. Une fois le processus de publication est terminée, cliquez sur **Terminer**.

12. Avant de passer à la section suivante appelée « Vérifier la coexistence du pool pilote avec le pool hérité » vous devez installer le Skype pour Business Server nouveau pilote pool frontal que nous avons simplement défini dans la topologie publiée, suivez les procédures décrites ici [Skype installer pour Business Server sur les serveurs de la topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. Une fois l’étape précédente est terminée, déplacez à la section suivante pour vérifier la coexistence du pool pilote avec le pool hérité.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

