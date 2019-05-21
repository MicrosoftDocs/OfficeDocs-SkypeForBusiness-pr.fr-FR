---
title: Déployer le pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: L’une des premières étapes requises pour la migration vers Skype entreprise Server 2019 consiste à déployer un pool de pilotes. Le pool de pilotes vous permet de tester la coexistence de Skype entreprise Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé l’ensemble des utilisateurs et des groupes vers Skype entreprise Server 2019.
ms.openlocfilehash: 3642d603b5923a554b8eca41a948125ef25526ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280863"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Déploiement du pool de pilotes Skype entreprise Server 2019

L’une des premières étapes requises pour la migration vers Skype entreprise Server 2019 consiste à déployer un pool de pilotes. Le pool de pilotes vous permet de tester la coexistence de Skype entreprise Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé l’ensemble des utilisateurs et des groupes vers Skype entreprise Server 2019. 
  
Lorsque vous déployez un pool de pilotes, vous utilisez l’Assistant définir un nouveau pool frontal. Vous devez déployer les mêmes fonctions et charges de travail dans votre liste de pilotes Skype entreprise Server 2019 que vous avez dans votre pool hérité. Si vous avez déployé un serveur d’archivage, un serveur de surveillance ou un gestionnaire d’opérations System Center Operations Manager permettant d’archiver ou de surveiller votre environnement hérité, et que vous voulez continuer à archiver ou à surveiller toute la migration, vous devez également déployer ces fonctionnalités dans votre environnement pilote. La version que vous avez déployée pour archiver ou surveiller votre environnement hérité ne capturera pas de données dans votre environnement 2019 Skype entreprise Server. 
  
> [!NOTE]
> La procédure suivante décrit les fonctionnalités et paramètres à envisager dans le cadre de votre processus global de déploiement de pool pilote. Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Pour déployer un pool de pilotes de Skype entreprise Server 2019

1. Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.
    
2. Développez l’arborescence jusqu’à ce que vous atteigniez **Skype entreprise Server Server 2019** > **Enterprise Edition**.
    
3. Cliquez avec le bouton droit sur **Pools frontals Enterprise Edition** et sélectionnez **nouveau pool frontal**.
  
4. Entrez le nom de domaine complet (FQDN) du pool. Lors de la définition de votre pool de pilotes, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition Server. Skype entreprise Server 2019 ne nécessite pas que les fonctionnalités de votre pool pilote correspondent aux éléments déployés dans votre pool hérité.
    
    > [!CAUTION]
    > Le nom de domaine complet (FQDN) du pool ou du serveur que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool hérité actuellement déployé ou à tout autre serveur actuellement déployé. 
  
5. Dans la page **Sélectionner des fonctionnalités** , activez les cases à cocher des fonctionnalités que vous voulez inclure dans ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée multipartie, mais pas la vérification de la Conférence rendez-vous (RTC), de la voix entreprise ou du contrôle d’admission des appels les zones, car elles représentent les fonctionnalités de conférence vocale, vidéo et de collaboration. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Dans la page **Sélectionner des rôles de serveurs** colocalisés, nous vous recommandons de choisir de Collocate le serveur de médiation dans Skype entreprise Server 2019. Lors de la fusion d’une topologie héritée avec Skype entreprise Server 2019, nous vous recommandons de commencer par collocate le serveur de médiation hérité. Après la fusion des topologies et la configuration du serveur de médiation Skype entreprise Server 2019, vous pouvez décider si vous souhaitez conserver le serveur de médiation colocalisé ou le modifier en serveur autonome lorsque vous déplacez le rôle serveur de médiation vers Skype entreprise Server. 2019 plus tard dans le processus de déploiement. 
   
7. Dans la page associez les **rôles de serveur à cette liste frontale** , pendant le déploiement du pool de pilotes, *ne sélectionnez pas* l’option **activer un pool Edge à utiliser par le composant multimédia de cette option de pool frontal** . Il s’agit d’une fonctionnalité que vous allez activer et mettre en ligne dans une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment. 
  
8. Dans la page **Sélectionner un serveur Office Web Apps** , cliquez sur **nouveau**, puis spécifiez le nom de domaine complet du serveur d’applications.
  
9. Dans la page **définir la banque SQL Server** , lors de la définition de SQL Server Store pour l’archivage et la surveillance de Skype entreprise Server, sélectionnez l’instance SQL Server créée précédemment pour Skype entreprise Server 2019. 
  
10. Pour publier votre topologie, cliquez avec le bouton droit sur le nœud du **serveur Skype entreprise** , puis cliquez sur **topologie de publication**.
  
11. Lorsque le processus de publication est terminé, cliquez sur **Terminer**.

12. Avant de passer à la section suivante intitulé «vérifier la coexistence du pool de pilotes avec le pool hérité», vous devez installer le nouveau pool de pilotes front end de Skype entreprise Server que nous venons de définir dans la topologie publiée, suivre les procédures décrites dans la section [Installer Skype pour Business Server sur des serveurs dans la topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. À la fin de l’étape précédente, passez à la section suivante pour vérifier la coexistence du pool pilote avec le pool hérité.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

