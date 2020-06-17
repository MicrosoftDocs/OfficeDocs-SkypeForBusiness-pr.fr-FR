---
title: Déployer le pool pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: L’une des premières étapes requises pour la migration vers Skype entreprise Server 2019 consiste à déployer un pool pilote. Le pool pilote est l’endroit où vous testez la coexistence de Skype entreprise Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé tous les utilisateurs et pools vers Skype entreprise Server 2019.
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752856"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Déployer le pool pilote de Skype entreprise Server 2019

L’une des premières étapes requises pour la migration vers Skype entreprise Server 2019 consiste à déployer un pool pilote. Le pool pilote est l’endroit où vous testez la coexistence de Skype entreprise Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé tous les utilisateurs et pools vers Skype entreprise Server 2019. 
  
Lorsque vous déployez un pool pilote, vous utilisez l’Assistant Définir un nouveau pool frontal. Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool pilote Skype entreprise Server 2019 que dans votre pool hérité. Si vous avez déployé le serveur d’archivage, le serveur de surveillance ou System Center Operations Manager pour l’archivage ou la surveillance de votre environnement hérité, et que vous souhaitez continuer l’archivage ou la surveillance pendant la migration, vous devez également déployer ces fonctionnalités dans votre environnement pilote. La version que vous avez déployée pour archiver ou surveiller votre environnement hérité ne capture pas les données dans votre environnement Skype entreprise Server 2019. 
  
> [!NOTE]
> La procédure qui suit traite des fonctionnalités et paramètres à considérer dans le cadre du processus de déploiement général de votre pool pilote. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Pour déployer un pool pilote de Skype entreprise Server 2019

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    
2. Développez l’arborescence jusqu’à **Skype for Business Server 2019**ce que vous atteigniez les  >  **Pools frontaux**de Skype entreprise Server 2019 Enterprise Edition.
    
3. Cliquez avec le bouton droit sur **Pools frontaux Enterprise Edition** et sélectionnez **nouveau pool frontal**.
  
4. Entrez le nom de domaine complet (FQDN) du pool. Lorsque vous définissez votre pool pilote, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition. Skype entreprise Server 2019 ne requiert pas que les fonctionnalités de votre pool pilote correspondent à ce qui a été déployé dans votre pool hérité.
    
    > [!CAUTION]
    > Le nom de domaine complet du pool ou du serveur que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool hérité actuellement déployé ou à d’autres serveurs actuellement déployés. 
  
5. Dans la page **Sélectionner les fonctionnalités**, activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée à plusieurs, mais n’activez pas les cases à cocher Conférence rendez-vous, voix entreprise ou contrôle d’admission des appels, car elles représentent des fonctionnalités de conférence vocale, vidéo et de collaboration. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Sur la page **Sélectionner des rôles serveur colocalisés** , nous vous recommandons de choisir de colocaliser le serveur de médiation dans Skype entreprise Server 2019. Lors de la fusion d’une topologie héritée avec Skype entreprise Server 2019, nous vous recommandons de commencer par colocaliser le serveur de médiation hérité. Après avoir fusionné les topologies et configuré le serveur de médiation Skype entreprise Server 2019, vous pouvez décider s’il faut conserver le serveur de médiation colocalisé ou le remplacer par un serveur autonome lorsque vous déplacez le rôle de serveur de médiation vers Skype entreprise Server 2019 plus tard dans le processus de déploiement. 
   
7. Sur la page **rôles serveur associés à ce pool frontal** , pendant le déploiement du pool pilote, *ne sélectionnez pas* l’option autoriser l’utilisation d’un pool de serveurs **Edge par le composant multimédia de ce pool frontal** . Il s’agit d’une fonctionnalité que vous activerez et mettrez en ligne lors d’une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment. 
  
8. Dans la page **Sélectionner un serveur Office Web Apps**, cliquez sur **Nouveau**, puis indiquez le nom de domaine complet du serveur d’applications.
  
9. Sur la page **définir le magasin SQL Server d’archivage** , lors de la définition du magasin SQL Server pour l’archivage et la surveillance de Skype entreprise Server, sélectionnez l’instance SQL Server créée précédemment pour Skype entreprise Server 2019. 
  
10. Pour publier votre topologie, cliquez avec le bouton droit sur le nœud du **serveur Skype entreprise** , puis cliquez sur **publier la topologie**.
  
11. Au terme du processus, cliquez sur **Terminer**.

12. Avant de passer à la section suivante intitulée « vérifier la coexistence du pool pilote avec le pool hérité », vous devez installer le nouveau pool pilote frontal Skype entreprise Server que nous venons de définir dans la topologie publiée, suivez les procédures décrites ici [Installer Skype entreprise Server sur les serveurs dans la topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .

13. Une fois l’étape précédente terminée, passez à la section suivante pour vérifier la coexistence du pool pilote avec le pool hérité.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

