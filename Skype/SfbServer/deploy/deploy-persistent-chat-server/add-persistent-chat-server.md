---
title: Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Résumé: pour plus d’informations sur l’ajout d’un serveur de chat permanent à votre topologie 2015 de Skype entreprise Server.'
ms.openlocfilehash: 7d5a61dd001c759eab4b168cb3543032de7b4fc4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239865"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server
 
**Résumé:** Pour plus d’informations sur l’ajout d’un serveur de chat permanent à votre topologie 2015 de Skype entreprise Server, reportez-vous à cette rubrique.
  
Une fois que vous avez installé le logiciel requis sur chaque serveur sur lequel vous envisagez de déployer le serveur de chat permanent, vous utilisez le générateur de topologie pour: 
  
- Mettre à jour votre topologie de façon à y inclure le serveur de conversation permanente
    
- Publication de la topologie mise à jour
    
> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Mettre à jour votre topologie de façon à y inclure le serveur de conversation permanente

Suivez les étapes ci-dessous pour installer une seule liste de serveurs de chat permanent sans configuration de reprise après sinistre. Pour configurer un pool de serveurs de chat permanent étiré pour une haute disponibilité et une reprise après sinistre, voir [configurer la haute disponibilité et la récupération après sinistre pour le serveur de chat permanent dans Skype entreprise server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Pour déployer plusieurs pools de serveurs de chat permanent, répétez la même procédure pour chaque liste.
  
1. Sur un ordinateur exécutant Skype entreprise Server ou sur lequel sont installés les outils d’administration de Skype entreprise Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie qui est requise pour l’installation de Skype entreprise Server, vous devez utiliser un compte membre du groupe **administrateurs de domaine** et de l' ** RTCUniversalServerAdmins** et qui dispose des autorisations de contrôle total (lecture, écriture et modification) sur le magasin de fichiers que vous allez utiliser pour le stockage de fichiers sur le serveur de chat permanent (de sorte que le générateur de topologie puisse configurer les DACL requis) ou un compte avec droits équivalents.
  
2. Démarrer le générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au nœud Pools de **conversations permanentes** et développez-le pour sélectionner un pool Skype entreprise Server, ou cliquez avec le bouton droit sur le nœud et sélectionnez **nouvelle liste de conversations permanentes**. Vous devez définir le nom de domaine complet (FQDN) du pool et indiquer s’il s’agit d’un pool de serveur unique ou d’un déploiement de pool multiserveur.
    
    Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**. Choisissez le premier si vous envisagez de disposer de plusieurs serveurs frontaux dans votre pool de serveurs de chat permanent. Effectuez ce choix maintenant, ou ultérieurement, car une fois que vous aurez créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs. Si vous choisissez un pool d’ordinateurs multiples, entrez le nom de chaque serveur frontal qui comprend le pool.
    
    > [!IMPORTANT]
    > Si le rôle serveur Chat permanent est installé sur un serveur Standard Edition Server, le nom de domaine complet doit correspondre au nom de domaine complet (FQDN) du serveur Standard Edition Server. 
  
4. Définissez un **nom complet** simple pour le pool de serveurs de chat permanent. Le nom d’affichage peut être utilisé par des clients personnalisés, en particulier s’il existe plusieurs pools de serveurs de chat permanent pour différencier des salles.
    
5. Définissez le port utilisé par le serveur de chat permanent pour communiquer avec les serveurs front-end Skype entreprise Server. Le port par défaut est 5041.
    
6. Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**. Le cas échéant, le service de conformité serveur Chat permanent est installé sur le même ordinateur que le serveur frontal de chat permanent du serveur. Vous êtes invité à sélectionner un serveur principal SQL Server pour la compatibilité avec le serveur Chat permanent plus tard.
    
7. Attribuez une affinité de site pour le pool de serveurs de chat permanent. Activez la case à cocher **utiliser ce pool \<comme\> option par défaut pour le site SiteName** ou **Utilisez ce pool par défaut pour tous les sites** pour désigner ce pool de serveurs de chat permanent comme pool par défaut pour le site actuel ou pour tous les sites. Lorsque le client Skype entreprise est utilisé pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’interface de création et de gestion de la salle pour pouvoir diriger les opérations de création et de gestion de la salle vers ce pool. Ce comportement s’applique uniquement lorsque vous avez déployé plusieurs pools de serveurs de chat permanent et que vous voulez utiliser les fonctionnalités de création et de gestion de la salle du serveur de chat permanent.
    
    > [!IMPORTANT]
    > Vous pouvez personnaliser les fonctionnalités de création et de gestion d’une salle à l’aide du kit de développement logiciel (SDK) serveur Chat permanent. 
  
8. Définissez le **SQL Store pour le serveur de chat permanent (emplacement de stockage du contenu d’une salle de conversation)** en effectuant l’une des opérations suivantes:
    
   - Pour utiliser un magasin SQL Server existant, dans la liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
    
   - Pour spécifier une nouvelle base de données SQL Server, cliquez sur **nouveau**, puis dans **définir un nouveau SQL Store**, procédez comme suit:
    
   - Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous voulez créer la nouvelle base de données SQL Server.
    
   - Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.
    
     > [!NOTE]
     > Pour plus d’informations sur la configuration des bases de données de sauvegarde SQL Server pour la récupération d’urgence, voir [configurer la haute disponibilité et la récupération d’urgence pour le serveur de chat permanent dans Skype entreprise server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Définissez le magasin de conformité SQL Server si vous avez activé la conformité.
    
    > [!IMPORTANT]
    > Pour plus d’informations sur la configuration des miroirs SQL Server pour une disponibilité élevée de la base de données serveur de chat permanent et de la base de données de conformité du serveur Chat permanent [ pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Définissez le magasin de fichiers. Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation). Dans le cas d’une topologie de serveur de chat permanent multiserveur, il doit s’agir d’un chemin UNC (Universal Naming Convention); dans le cas d’une topologie de serveur de chat permanent d’un serveur unique, il peut s’agir d’un chemin d’accès de fichier local.
    
    Pour utiliser un magasin de fichiers existant, procédez ainsi :
    
    - Dans **Nom de domaine complet du serveur de fichiers**, indiquez le nom de domaine complet de l’ordinateur sur lequel vous voulez créer le nouveau magasin de fichiers.
    
    - Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.
    
      > [!IMPORTANT]
      > Vous pouvez définir le magasin de fichiers dans le générateur de topologie avant de créer le magasin de fichiers, mais vous devez créer le magasin de fichiers à l’emplacement défini que vous définissez avant de publier la topologie. Si le magasin de fichiers n’existe pas déjà, les tentatives de publication de la topologie échoueront. 
  
11. Sélectionnez le pool de serveurs frontal à utiliser comme tronçon suivant pour ce pool de serveurs de chat permanent. Il s’agit du pool de serveurs frontal qui sera en mesure d’acheminer les demandes de serveur de chat permanent vers ce pool.
    
12. Pour enregistrer la configuration, cliquez sur **Terminer**. Le pool de serveurs de chat permanent apparaît dans le générateur de topologie accompagné de vos paramètres de réserve spécifiques.
    
    Pour publier votre topologie mise à jour sur laquelle vous avez ajouté un serveur de conversation permanente, voir publier la topologie mise à jour.
    
    > [!NOTE]
    > Lorsque le générateur de topologie est déjà ouvert, vous pouvez passer à l’étape 3 de la rubrique publier la topologie mise à jour pour commencer à publier votre topologie mise à jour. 
  
## <a name="publish-the-updated-topology"></a>Publication de la topologie mise à jour
<a name="BKMK_PublishTopology"> </a>

Après avoir effectué la mise à jour de votre topologie dans le générateur de topologie, vous devez publier la topologie dans le centre de gestion central avant de pouvoir configurer et utiliser Skype entreprise Server. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.
  
Avant de publier votre topologie, installez les bases de données pour le serveur de chat permanent. Utilisez le générateur de topologie pour installer des bases de données en sélectionnant **action** et **installer la base de données**.
  
1. Sur un ordinateur exécutant Skype entreprise Server ou sur lequel sont installés les outils d’administration de Skype entreprise Server, connectez-vous à l’aide d’un compte membre du groupe administrateurs de **domaine** et du groupe **RTCUniversalServerAdmins** . et qui dispose des autorisations de contrôle total (lecture, écriture et modification) sur le magasin de fichiers à utiliser pour le stockage de fichiers du serveur de chat permanent (de sorte que le générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire requises), ou un compte avec un utilisateur équivalent Mission.
    
2. Démarrer le générateur de topologie. Sélectionnez **Ouvrir une topologie depuis un fichier local** si vous l’avez enregistrée localement.
    
3. Dans l’arborescence de la console, cliquez avec le bouton droit sur **Skype entreprise Server 2015**, puis cliquez sur **publier la topologie**.
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    

