---
title: Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Résumé : Lisez cette rubrique pour découvrir comment ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015.'
---

# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015.
  
Après avoir installé le logiciel prérequis sur chaque serveur sur lequel vous prévoyez de déployer le serveur de conversation permanente, vous utilisez le Générateur de topologie pour : 
  
- Mettre à jour votre topologie pour inclure le serveur de conversation permanente
    
- Publier la topologie mise à jour
    
> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Mettre à jour votre topologie pour inclure le serveur de conversation permanente

Effectuez les étapes suivantes pour installer un pool de serveurs de conversation permanente unique sans configuration de récupération d’urgence. Pour configurer un pool de serveurs de conversation permanente étiré pour la haute disponibilité et la récupération d’urgence, voir [Configure high availability and disaster recovery for Persistent Chat Server in Skype Entreprise Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Pour déployer plusieurs pools de serveurs de conversation permanente, répétez le même processus pour chaque pool.
  
1. Sur un ordinateur qui exécute Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local, mais pour publier une topologie requise pour installer Skype Entreprise Server, vous devez utiliser un compte membre du groupe **Administrateurs** du domaine et du groupe **RTCUniversalServerAdmins**.  et qui dispose d’autorisations de contrôle total (lecture, écriture et modification) sur le magasin de fichiers que vous allez utiliser pour le magasin de fichiers du serveur de conversation permanente (afin que le Générateur de topologie puisse configurer les DAC requises) ou un compte avec des droits équivalents.
  
2. Démarrez le Générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au nœud **Pools** de conversation permanente et développez-le pour sélectionner un pool Skype Entreprise Server ou cliquez avec le bouton droit sur le nœud et sélectionnez Nouveau pool de conversation **permanente**. Vous devez définir le nom de domaine complet (FQDN) du pool et indiquer si le pool sera un déploiement de pool à serveur unique ou à plusieurs serveurs.
    
    Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**. Choisissez le premier si vous envisagez d’avoir plusieurs serveurs frontux dans votre pool de serveurs de conversation permanente. Effectuez ce choix maintenant, ou ultérieurement, car une fois créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs. Si vous choisissez un pool de plusieurs ordinateurs, entrez les noms des serveurs frontux individuels qui composent le pool.
    
    > [!IMPORTANT]
    > Si le rôle serveur de conversation permanente est en cours d’installation sur un serveur Édition Standard, le nom de groupe doit correspondre au nom de Édition Standard serveur. 
  
4. Définissez un nom **complet** simple pour le pool de serveurs de conversation permanente. Le nom d’affichage peut être utilisé par des clients personnalisés, en particulier lorsqu’il existe plusieurs pools de serveurs de conversation permanente pour différencier les salles.
    
5. Définissez le port utilisé par le serveur de conversation permanente pour communiquer avec Skype Entreprise Server serveurs frontux. Le port par défaut est 5041.
    
6. Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**. Si c’est le cas, le service de conformité du serveur de conversation permanente est installé sur le même ordinateur que le serveur frontal du serveur de conversation permanente. Vous êtes invité à sélectionner ultérieurement un serveur SQL Server principal pour la conformité du serveur de conversation permanente.
    
7. Affectez l’affinité de site au pool de serveurs de conversation permanente. Sélectionnez la case à cocher Utiliser ce pool par défaut pour le **site \<SiteName\>** ou Utilisez ce pool par défaut pour tous les **sites** afin de désigner ce pool de serveurs de conversation permanente comme pool par défaut pour le site actuel ou tous les sites. Lorsque le client Skype Entreprise est utilisé pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’expérience de création et de gestion de salle afin qu’il puisse router les opérations de création et de gestion de salle vers ce pool. Cela s’applique uniquement lorsque plusieurs pools de serveurs de conversation permanente sont déployés et que vous souhaitez utiliser les fonctionnalités de création et de gestion de salle du serveur de conversation permanente.
    
    > [!IMPORTANT]
    > Vous pouvez personnaliser les fonctionnalités de création et de gestion de salle à l’aide du Kit de développement logiciel (SDK) du serveur de conversation permanente. 
  
8. Définissez **le magasin SQL de** conversation permanente pour le serveur principal de conversation permanente (où le contenu de la salle de conversation est stocké) en faisant l’une des opérations suivantes :
    
   - Pour utiliser un magasin SQL Server existant, dans la liste de listes listes, cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser.
    
   - Pour spécifier une nouvelle base SQL Server de données, cliquez sur **Nouveau, puis** dans Définir **SQL Store**, effectuez les choses suivantes :
    
   - Dans **SQL Server FQDN**, spécifiez le FQDN du SQL Server sur lequel vous souhaitez créer la nouvelle base de données SQL Server données.
    
   - Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.
    
     > [!NOTE]
     > Pour plus d’informations sur la configuration des bases de données de sauvegarde SQL Server pour la récupération d’urgence, voir [Configure high availability and disaster recovery for Persistent Chat Server in Skype Entreprise Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Définissez le SQL Server de conformité si vous avez activé la conformité.
    
    > [!IMPORTANT]
    > Pour plus d’informations sur la configuration des miroirs SQL Server pour la haute disponibilité de la base de données du serveur de conversation permanente et de la base de données de conformité du serveur de conversation permanente, voir [Configure high availability and disaster recovery for Persistent Chat Server in Skype Entreprise Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Définissez le magasin de fichiers. Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation). Dans le cas d’une topologie de serveur de conversation permanente à plusieurs serveurs, il doit s’agit d’un chemin d’accès UNC (Universal Naming Convention). et pour une topologie de serveur de conversation permanente à serveur unique, il peut s’agit d’un chemin d’accès au fichier local.
    
    Pour utiliser un magasin de fichiers existant, procédez ainsi :
    
    - Dans **le FQDN** du serveur de fichiers, spécifiez le nom de l’ordinateur sur lequel vous souhaitez créer le nouveau magasin de fichiers.
    
    - Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.
    
      > [!IMPORTANT]
      > Vous pouvez définir le magasin de fichiers dans le Générateur de topologie avant de créer le magasin de fichiers, mais vous devez créer le magasin de fichiers à l’emplacement défini avant de publier la topologie. Si le magasin de fichiers n’existe pas encore, les tentatives de publication de la topologie échouent. 
  
11. Sélectionnez le pool de serveurs frontux à utiliser comme saut suivant pour ce pool de serveurs de conversation permanente. Il s’agit du pool de serveurs frontux qui pourra router les demandes de serveur de conversation permanente vers ce pool.
    
12. Pour enregistrer la configuration, cliquez sur **Terminer**. Le pool de serveurs de conversation permanente apparaît dans le Générateur de topologie, accompagné de vos paramètres de pool spécifiques.
    
    Pour publier votre topologie mise à jour à laquelle vous avez ajouté le serveur de conversation permanente, voir Publier la topologie mise à jour.
    
    > [!NOTE]
    > Avec le Générateur de topologie déjà ouvert, vous pouvez passer à l’étape 3 de la publication de la topologie mise à jour pour commencer la publication de votre topologie mise à jour. 
  
## <a name="publish-the-updated-topology"></a>Publier la topologie mise à jour
<a name="BKMK_PublishTopology"> </a>

Après avoir mis à jour votre topologie dans le Générateur de topologie, vous devez la publier dans le magasin central de gestion avant de pouvoir configurer et utiliser Skype Entreprise Server. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.
  
Avant de publier votre topologie, installez les bases de données pour le serveur de conversation permanente. Utilisez le Générateur de topologie pour installer des bases de données en sélectionnant **Action** et **Installer la base de données**.
  
1. Sur un ordinateur exécutant Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe **Administrateurs** du domaine et du **RTCUniversalServerAdmins**  et qui dispose des autorisations de contrôle total (lecture, écriture et modification) sur le magasin de fichiers à utiliser pour le magasin de fichiers du serveur de conversation permanente (afin que le Générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire (DACL) requises) ou un compte avec des droits d’utilisateur équivalents.
    
2. Démarrez le Générateur de topologie. **Sélectionnez Ouvrir la topologie à partir d’un fichier local** si vous l’avez enregistré localement.
    
3. Dans l’arborescence de la console, cliquez **Skype Entreprise Server 2015**, puis cliquez sur **Publier la topologie**.
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    

