---
title: Ajouter serveur de Chat permanente à votre Skype pour la topologie de Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Résumé : Lisez cette rubrique pour savoir comment ajouter de serveur de Chat persistant à votre Skype pour Business Server 2015 topologie.'
ms.openlocfilehash: 3d00e24dbe8f25b2a1887b8c1c79a63bda3471f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Ajouter serveur de Chat permanente à votre Skype pour la topologie de Business Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment ajouter de serveur de Chat persistant à votre Skype pour Business Server 2015 topologie.
  
Après avoir installé les logiciels requis sur chaque serveur sur lequel vous envisagez de déployer persistant Chat Server, vous utilisez le Générateur de topologies pour : 
  
- Mettre à jour votre topologie de façon à y inclure le serveur de conversation permanente
    
- Publier la topologie mise à jour
    
## <a name="update-your-topology-to-include-persistent-chat-server"></a>Mettre à jour votre topologie de façon à y inclure le serveur de conversation permanente

Effectuez les opérations suivantes pour l’installation d’un pool unique de serveur de conversation persistant sans une configuration de récupération après sinistre. Pour configurer un pool permanent Chat Server étiré pour la haute disponibilité et reprise après sinistre, consultez [configurer la haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Pour déployer plusieurs pools persistant Chat Server, répétez ce processus pour chaque pool.
  
1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour outils d’administration de Business Server sont installés, ouvrez une session en utilisant un compte qui est membre du groupe d’utilisateurs local (ou un compte avec des droits d’utilisateur équivalent).
    
    > [!NOTE]
    > Vous pouvez définir une topologie en utilisant un compte qui est membre du groupe d’utilisateurs local, mais pour publier une topologie qui est requis pour installer Skype pour Business Server, vous devez utiliser un compte qui est membre du groupe **Admins** du domaine et de la ** RTCUniversalServerAdmins** groupe et qui dispose d’autorisations de contrôle total (lire, écrire et modifier) dans le magasin de fichiers que vous souhaitez utiliser pour le magasin de fichiers serveur de Chat persistant (afin que le Générateur de topologies peut configurer les listes DACL requis), ou un compte droits équivalents.
  
2. Démarrer le Générateur de topologies.
    
3. Dans l’arborescence de la console, naviguez vers le nœud **Pools de conversation permanents** et développez-le pour sélectionnez un Skype pour un pool de serveurs d’entreprise, ou cliquez sur le nœud et sélectionnez **Nouveau Pool persistant de Chat**. Vous devez définir le nom de domaine complet du pool (FQDN) et indiquer si ce pool doit être un pool de serveur unique ou un déploiement de plusieurs serveurs pool.
    
    Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**. Choisissez le premier si vous prévoyez d’avoir plus d’un serveur frontal dans votre pool de serveur de conversation persistant. Effectuez ce choix maintenant, ou ultérieurement, car une fois que vous aurez créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs. Si vous choisissez un pool ordinateur plusieurs, entrez les noms des différents serveurs frontaux qui composent le pool.
    
    > [!IMPORTANT]
    > Si le rôle de serveur de conversation permanent est installé sur un serveur Standard Edition server, le nom de domaine complet doit correspondre le nom de domaine complet du serveur Standard Edition. 
  
4. Définir un simple **Nom d’affichage** pour le pool de serveur de conversation persistant. Le nom d’affichage utilisable par les clients personnalisés, en particulier lorsqu’il existe plusieurs pools de serveur de Chat persistant pour différencier les salles.
    
5. Définissez le port utilisé par le serveur Chat persistant pour communiquer avec Skype pour Business Server serveurs frontaux. Le port par défaut est 5041.
    
6. Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**. Si sélectionné, le service persistant conformité du serveur Chat est installé sur le même ordinateur que le persistant Chat Server serveur frontal. Vous êtes invité à sélectionner un SQL Server serveur principal persistants conformité du serveur Chat, ultérieurement.
    
7. Attribuer une affinité pour le pool de serveur de conversation persistant. Sélectionnez le **utiliser ce pool par défaut pour le site \<SiteName\> ** case ou **utiliser ce pool par défaut pour tous les sites** pour désigner ce pool de serveur de conversation persistant en tant que le pool par défaut pour le site en cours ou tous les sites. Lorsque le Skype pour client d’entreprise est utilisé pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’expérience de création et de gestion d’espace afin que les opérations de création et de gestion de salle d’acheminer vers ce pool. Cela s’applique uniquement lorsque vous avez déployés plusieurs pools de persistant Chat Server et que vous souhaitez utiliser les fonctionnalités de création et la gestion de salle de serveur de Chat persistant.
    
    > [!IMPORTANT]
    > Vous pouvez personnaliser les fonctionnalités de création et la gestion d’espace utilisant le persistant Chat Server logiciel Kit de développement (SDK). 
  
8. Définir le **magasin de SQL pour le persistant Chat Server Back-End (contenu de la salle de stockage)** en effectuant l’une des opérations suivantes :
    
   - Pour utiliser une banque existante de SQL Server, dans la liste déroulante, cliquez sur le nom de la banque d’informations de SQL Server que vous souhaitez utiliser.
    
   - Pour spécifier une nouvelle base de données SQL Server, cliquez sur **Nouveau**et de **Définir, nouveau magasin SQL**, effectuez les opérations suivantes :
    
   - Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet de la SQL Server sur lequel vous souhaitez créer la nouvelle base de données SQL Server.
    
   - Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.
    
    > [!NOTE]
    > Pour plus d’informations sur la façon de configurer les bases de données de sauvegarde SQL Server pour la reprise après sinistre, reportez-vous à la section [configurer la haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Définir le magasin de conformité SQL Server si vous avez activé la mise en conformité.
    
    > [!IMPORTANT]
    > Pour plus d’informations sur la configuration des miroirs de SQL Server pour une haute disponibilité de la base de données du serveur de conversation persistant et la base de données de conformité permanente Chat Server, reportez-vous à la section [configuration haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Définissez le magasin de fichiers. Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation). Dans le cas d’une topologie de serveur de Chat persistant de plusieurs serveurs, ce doit être un chemin d’accès UNC Universal Naming Convention () ; et d’une topologie de serveur de conversation persistant à serveur unique, il peut être un chemin d’accès du fichier local.
    
    Pour utiliser un magasin de fichiers existant, procédez ainsi :
    
    - Dans **Nom de domaine complet du serveur de fichiers**, indiquez le nom de domaine complet de l’ordinateur sur lequel vous voulez créer le nouveau magasin de fichiers.
    
    - Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.
    
     > [!IMPORTANT]
     > Avant de vous créez le magasin de fichiers, mais vous devez créer le magasin de fichiers dans l’emplacement défini, que vous définissez avant de publier la topologie, vous pouvez définir l’emplacement du fichier dans le Générateur de topologies. Si le magasin de fichiers n’existe pas déjà, les tentatives de publication de la topologie échoueront. 
  
11. Sélectionnez le pool de serveur frontal à utiliser comme un saut suivant pour ce pool de serveur de conversation persistant. C’est le pool de serveur frontal qui sera en mesure de router les demandes permanentes Chat Server à ce pool.
    
12. Pour enregistrer la configuration, cliquez sur **Terminer**. Le pool de serveur de conversation persistant s’affiche dans le Générateur de topologies accompagnés par des paramètres de pool spécifique.
    
    Pour publier votre topologie mis à jour auxquels vous avez ajouté persistant Chat Server, reportez-vous à la section Publier la topologie mis à jour.
    
    > [!NOTE]
    > Avec le Générateur de topologies est déjà ouvert, vous pouvez procéder à l’étape 3 de publier la topologie mis à jour pour commencer à publier votre topologie mis à jour. 
  
## <a name="publish-the-updated-topology"></a>Publication de la topologie mise à jour
<a name="BKMK_PublishTopology"> </a>

Après la mise à jour de votre topologie dans le Générateur de topologie, vous devez publier la topologie pour le magasin Central de gestion avant de pouvoir configurer et utiliser Skype pour Business Server. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.
  
Avant de publier votre topologie, installer les bases de données de serveur de conversation persistant. Générateur de topologies permet d’installer les bases de données en sélectionnant une **Action** et **Installer la base de données**.
  
1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour outils d’administration de Business Server sont installés, ouvrez une session en utilisant un compte qui est un membre du groupe **Admins** du domaine et du groupe **RTCUniversalServerAdmins** , et qui dispose d’autorisations de contrôle total (lire, écrire et modifier) dans le magasin de fichiers à utiliser pour le magasin de fichiers serveur de Chat persistant (afin que le Générateur de topologies peut configurer les listes de contrôle d’accès discrétionnaire requis (DACL)), ou un compte d’utilisateur équivalent droits.
    
2. Démarrer le Générateur de topologies. Sélectionnez **Ouvrir une topologie depuis un fichier local** si vous l’avez enregistrée localement.
    
3. Dans l’arborescence de la console, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Publier la topologie**.
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    

