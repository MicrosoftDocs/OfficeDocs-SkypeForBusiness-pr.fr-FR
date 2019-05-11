---
title: Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Résumé : Lisez cette rubrique pour savoir comment ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie.'
ms.openlocfilehash: edd04ce781c3f91190b2c7baf9e0575f6dba5b1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894499"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie
 
**Résumé :** Lisez cette rubrique pour savoir comment ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie.
  
Après avoir installé le logiciel requis sur chaque serveur sur lequel vous souhaitez déployer des serveurs de conversation permanente, vous utilisez le Générateur de topologie pour : 
  
- Mettre à jour votre topologie de façon à y inclure le serveur de conversation permanente
    
- Publication de la topologie mise à jour
    
> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Mettre à jour votre topologie de façon à y inclure le serveur de conversation permanente

Effectuez les étapes suivantes pour installer un seul pool de serveurs de conversation permanente sans une configuration de récupération d’urgence. Pour configurer un pool de serveurs de conversation permanente étiré de haute disponibilité et récupération d’urgence, consultez [configuration de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Pour déployer plusieurs pools de serveurs de conversation permanente, répétez la même procédure pour chaque pool.
  
1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour les outils d’administration Business Server sont installés, ouvrez une session en utilisant un compte qui est membre du groupe utilisateurs local (ou un compte disposant de droits utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie en utilisant un compte qui est un membre du groupe utilisateurs local, mais pour publier une topologie qui est requis pour installer Skype pour Business Server, vous devez utiliser un compte qui est membre du groupe **Admins** du domaine et le ** RTCUniversalServerAdmins** groupe et qui dispose d’autorisations Contrôle total (lire, écrire et modifier) sur le magasin de fichiers que vous allez utiliser pour le magasin de fichiers serveur de conversation permanente (afin que le Générateur de topologie peuvent configurer les DACL requis), ou d’un compte avec droits équivalents.
  
2. Démarrez le Générateur de topologie.
    
3. Dans l’arborescence de la console, naviguez jusqu’au nœud **Pools de conversation permanente** et la développer pour sélectionner un Skype pour le pool de serveurs d’entreprise, ou cliquez sur le nœud et sélectionnez **Nouveau Pool de conversations permanentes**. Vous devez définir le nom de domaine complet du pool (FQDN) et indiquer si le pool doit être un pool de serveur unique ou d’un déploiement de pool de plusieurs serveurs.
    
    Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**. Si vous envisagez d’avoir plus d’un serveur frontal dans votre pool de serveurs de conversation permanente, cliquez sur le premier. Effectuez ce choix maintenant, ou ultérieurement, car une fois que vous aurez créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs. Si vous choisissez un pool de plusieurs ordinateurs, entrez les noms des individuels serveurs frontaux qui composent le pool.
    
    > [!IMPORTANT]
    > Si le rôle de serveur de conversation permanente est installé sur un serveur Standard Edition server, le nom de domaine complet doit correspondre à celui du serveur Standard Edition. 
  
4. Définir un simple **Nom d’affichage** pour le pool de serveurs de conversation permanente. Le nom d’affichage utilisable par les clients personnalisés, notamment lorsqu’il existe plusieurs pools de serveurs de conversation permanente pour différencier les salles.
    
5. Définissez le port utilisé par le serveur de conversation permanente pour communiquer avec Skype pour les serveurs frontaux Business Server. Le port par défaut est 5041.
    
6. Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**. Si vous choisissez, le service de conformité de serveur de conversation permanente est installé sur le même ordinateur que le Persistent Chat Server serveur frontal. Vous êtes invité à sélectionner un SQL Server serveur principal pour la conformité de conversation permanente de serveur ultérieurement.
    
7. Attribuer une affinité pour le pool de serveurs de conversation permanente. Sélectionnez le **utiliser ce pool comme valeur par défaut pour le site \<SiteName\> ** case à cocher ou **ce pool comme valeur par défaut pour tous les sites** pour désigner ce pool de serveurs de conversation permanente que le pool par défaut pour le site actuel ou tous les sites. Lorsque le Skype pour client d’entreprise est utilisée pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’expérience de création et la gestion de salle afin qu’elle peut acheminer les opérations de création et la gestion de salle à ce pool. Cela s’applique uniquement lorsque vous avez plusieurs pools Persistent Chat Server déployés et que vous souhaitez utiliser les fonctionnalités de création et la gestion de salle du serveur de conversation permanente.
    
    > [!IMPORTANT]
    > Vous pouvez personnaliser les fonctionnalités de création et gestion de salle à l’aide de la Persistent Chat Server logiciel Kit de développement (SDK). 
  
8. Définir le **magasin de SQL pour la Persistent Chat Server frontal (où est stocké le contenu de salle de conversation)** en effectuant l’une des options suivantes :
    
   - Pour utiliser un magasin SQL Server existant, dans la liste déroulante, cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser.
    
   - Pour spécifier une nouvelle base de données SQL Server, cliquez sur **Nouveau**et dans **Définir un nouveau magasin SQL**, procédez comme suit :
    
   - Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur SQL sur lequel vous souhaitez créer la nouvelle base de données SQL Server.
    
   - Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.
    
     > [!NOTE]
     > Pour plus d’informations sur la façon de configurer les bases de données de sauvegarde SQL Server pour la récupération d’urgence, voir [configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Définir le magasin de conformité SQL Server si vous avez activé la conformité.
    
    > [!IMPORTANT]
    > Pour plus d’informations sur la configuration des miroirs SQL Server pour une haute disponibilité pour la base de données du serveur de conversation permanente et la base de données de conformité Persistent Chat Server, voir Configure [haute disponibilité et récupération d’urgence pour le serveur de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Définissez le magasin de fichiers. Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation). Dans le cas d’une topologie de serveur de conversation permanente plusieurs serveurs, il doit être un chemin d’accès UNC Universal Naming Convention () ; et pour une topologie de serveur de conversation permanente serveur unique, il peut être un chemin d’accès du fichier local.
    
    Pour utiliser un magasin de fichiers existant, procédez ainsi :
    
    - Dans **Nom de domaine complet du serveur de fichiers**, indiquez le nom de domaine complet de l’ordinateur sur lequel vous voulez créer le nouveau magasin de fichiers.
    
    - Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.
    
      > [!IMPORTANT]
      > Vous pouvez définir le magasin de fichiers dans le Générateur de topologie avant que vous créez le magasin de fichiers, mais vous devez créer le magasin de fichiers à l’emplacement défini, que vous définissez avant de publier la topologie. Si le magasin de fichiers n’existe pas déjà, les tentatives de publication de la topologie échoueront. 
  
11. Sélectionnez le pool de serveur frontal à utiliser comme tronçon suivant pour ce pool de serveurs de conversation permanente. Il s’agit du pool de serveurs frontaux qui est en mesure d’acheminer les requêtes de serveur de conversation permanente à ce pool.
    
12. Pour enregistrer la configuration, cliquez sur **Terminer**. Le pool de serveurs de conversation permanente apparaît dans le Générateur de topologie accompagnés de vos paramètres de pool spécifique.
    
    Pour publier votre topologie mise à jour à laquelle vous avez ajouté des serveurs de conversation permanente, voir publier la topologie mise à jour.
    
    > [!NOTE]
    > Avec le Générateur de topologie déjà ouvert, vous pouvez passer à l’étape 3 de publier la topologie mise à jour pour commencer à publier votre topologie mise à jour. 
  
## <a name="publish-the-updated-topology"></a>Publication de la topologie mise à jour
<a name="BKMK_PublishTopology"> </a>

Après la mise à jour de votre topologie dans le Générateur de topologie, vous devez publier la topologie dans le magasin Central de gestion avant de pouvoir configurer et utiliser Skype pour Business Server. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.
  
Avant de publier votre topologie, installez les bases de données pour le serveur de conversation permanente. Utilisez le Générateur de topologie pour installer les bases de données en sélectionnant **l’Action** et **Installer une base de données**.
  
1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour les outils d’administration Business Server sont installés, ouvrez une session en utilisant un compte qui est membre du groupe **Admins** du domaine et du groupe **RTCUniversalServerAdmins** , et qui dispose d’autorisations Contrôle total (lire, écrire et modifier) sur le magasin de fichiers à utiliser pour le magasin de fichiers serveur de conversation permanente (afin que le Générateur de topologie peuvent configurer les listes de contrôle d’accès discrétionnaire requises (DACL)), ou un compte d’utilisateur équivalents droits.
    
2. Démarrez le Générateur de topologie. Sélectionnez **Ouvrir une topologie depuis un fichier local** si vous l’avez enregistrée localement.
    
3. Dans l’arborescence de la console, avec le bouton droit **Skype pour Business Server 2015**, puis cliquez sur **Publier la topologie**.
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    

