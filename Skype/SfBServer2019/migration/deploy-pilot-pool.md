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
ms.localizationpriority: medium
description: L’une des premières étapes requises pour la migration vers Skype Entreprise Server 2019 consiste à déployer un pool pilote. Le pool pilote est l’endroit où vous testez la coexistence Skype Entreprise Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu’à ce que vous avez déplacé tous les utilisateurs et pools vers Skype Entreprise Server 2019.
ms.openlocfilehash: e69e42e95ce7d13d8da88e91d6f1c266d7449f7b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614988"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Déployer Skype Entreprise Server pool pilote 2019

L’une des premières étapes requises pour la migration vers Skype Entreprise Server 2019 consiste à déployer un pool pilote. Le pool pilote est l’endroit où vous testez la coexistence Skype Entreprise Server 2019 avec votre déploiement hérité. La coexistence est un état temporaire qui dure jusqu’à ce que vous avez déplacé tous les utilisateurs et pools vers Skype Entreprise Server 2019. 
  
Lorsque vous déployez un pool pilote, vous utilisez l’Assistant Définir un nouveau pool frontal. Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool pilote Skype Entreprise Server 2019 que dans votre pool hérité. Si vous avez déployé le serveur d’archivage, le serveur de surveillance ou System Center Operations Manager pour l’archivage ou la surveillance de votre environnement hérité et que vous souhaitez poursuivre l’archivage ou la surveillance tout au long de la migration, vous devez également déployer ces fonctionnalités dans votre environnement pilote. La version que vous avez déployée pour archiver ou surveiller votre environnement hérité ne capture pas les données dans votre environnement Skype Entreprise Server 2019. 
  
> [!NOTE]
> La procédure qui suit traite des fonctionnalités et paramètres à considérer dans le cadre du processus de déploiement général de votre pool pilote. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Pour déployer un pool pilote Skype Entreprise Server 2019

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    
2. Développez l’arborescence **jusqu’à ce que Skype Entreprise Server 2019** Êdition Entreprise pools  >  **frontux.**
    
3. Cliquez avec le bouton **droit Êdition Entreprise pools frontux** et sélectionnez **Nouveau pool frontal.**
  
4. Entrez le nom de domaine complet (FQDN) du pool. Lorsque vous définissez votre pool pilote, vous pouvez choisir de déployer un pool frontal Êdition Entreprise ou un serveur Édition Standard serveur. Skype Entreprise Server 2019 ne nécessite pas que les fonctionnalités de votre pool pilote correspondent à ce qui a été déployé dans votre pool hérité.
    
    > [!CAUTION]
    > Le nom de pool ou de serveur que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool hérité actuellement déployé ou à d’autres serveurs actuellement déployés. 
  
5. Dans la page **Sélectionner les fonctionnalités**, activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal. Par exemple, si vous déployez uniquement des fonctionnalités de messagerie instantanée et de présence, cochez la case Conférence pour autoriser la messagerie instantanée à plusieurs, mais vous ne sélectionnez pas les cases à cocher Conférence rendez-vous (PSTN), Voix Entreprise ou Contrôle d’admission des appels, car elles représentent des fonctionnalités de conférence vocale, vidéo et collaborative. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Dans **la** page Sélectionner des rôles de serveur cococérés, nous vous recommandons de choisir de cérer le serveur de médiation dans Skype Entreprise Server 2019. Lors de la fusion d’une topologie héritée avec Skype Entreprise Server 2019, nous exigeons que vous coloyiez d’abord le serveur de médiation hérité. Après avoir fusion des topologies et configuré le serveur de médiation Skype Entreprise Server 2019, vous pouvez décider s’il faut conserver le serveur de médiation cingéré ou le modifier en serveur autonome lorsque vous déplacez le rôle serveur de médiation vers Skype Entreprise Server 2019 plus loin dans le processus de déploiement. 
   
7. Dans la page Associer des rôles serveur à ce **pool** frontal, pendant le déploiement du pool *pilote,* ne choisissez pas l’option Activer un pool de serveurs Edge à utiliser par le composant multimédia de cette option de **pool frontal.** Il s’agit d’une fonctionnalité que vous activerez et mettrez en ligne lors d’une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment. 
  
8. Dans la page **Sélectionner un serveur Office Web Apps**, cliquez sur **Nouveau**, puis indiquez le nom de domaine complet du serveur d’applications.
  
9. Dans la **page** Définir le magasin SQL Server d’archivage, lors de la définition du magasin SQL Server pour l’archivage et la surveillance Skype Entreprise Server, sélectionnez l’instance SQL Server créée précédemment pour Skype Entreprise Server 2019. 
  
10. Pour publier votre topologie, cliquez avec le bouton droit sur **le Skype Entreprise Server,** puis cliquez sur **Publier la topologie.**
  
11. Au terme du processus, cliquez sur **Terminer**.

12. Avant de passer à la section suivante appelée « Vérifier la coexistence du pool pilote avec le pool hérité », vous devez installer [](../../SfbServer/deploy/install/install-skype-for-business-server.md) le nouveau pool pilote frontal Skype Entreprise Server que nous venons de définir dans la topologie publiée, suivez les procédures décrites ici Pour installer Skype Entreprise Server sur les serveurs de la topologie

13. Une fois l’étape précédente terminée, déplacez-vous vers la section suivante pour vérifier la coexistence du pool pilote avec le pool hérité.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
