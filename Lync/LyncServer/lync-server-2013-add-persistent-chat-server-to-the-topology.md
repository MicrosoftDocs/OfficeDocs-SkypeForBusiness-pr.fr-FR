---
title: 'Lync Server 2013 : ajout d’un serveur de conversation permanente à la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ae7ca7e475fd106608dea09fedf250ef541a5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Ajouter un serveur de conversation permanente à la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Vous devez incorporer la prise en charge de Lync Server 2013 et du serveur de conversation permanente dans votre topologie avant de pouvoir configurer votre déploiement pour prendre en charge le serveur de conversation permanente. Les informations contenues dans cette rubrique expliquent comment utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à votre topologie existante.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Pour ajouter un serveur de conversation permanente à une topologie

Procédez comme suit pour installer un seul pool de serveurs de conversation permanente sans une configuration de récupération d’urgence. Pour configurer un pool de serveurs de conversation permanente étiré pour la haute disponibilité et la récupération d’urgence, reportez-vous à la rubrique [configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.

Pour déployer plusieurs pools de serveurs de conversation permanente, répétez la même procédure pour chaque pool.

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe utilisateurs local (ou d’un compte doté de droits d’utilisateur équivalents).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour publier une topologie, qui est nécessaire pour installer un serveur Lync Server 2013, vous devez utiliser un compte membre du groupe <STRONG>administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> et qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le magasin de fichiers que vous allez utiliser pour le magasin de fichiers du serveur de conversation permanente (c’est-à-dire que le générateur de topologies peut configurer les DACL requises) ou un compte disposant de droits équivalents.

    
    </div>

2.  Démarrez le Générateur de topologie.

3.  Dans l’arborescence de la console, accédez au nœud **pools de conversations permanentes** et développez-le pour sélectionner un pool de serveurs de conversation permanente, ou cliquez avec le bouton droit sur le nœud et sélectionnez **nouveau pool de conversations permanentes**. Vous devez définir le nom de domaine complet (FQDN) du pool et indiquer si le pool sera un déploiement de pool à serveur unique ou à plusieurs serveurs.
    
    Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**. Choisissez le premier si vous envisagez d’avoir plusieurs serveurs frontaux de serveur de conversation permanente dans votre pool de serveurs de conversation permanente. Effectuez ce choix maintenant, ou ultérieurement, car une fois créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs. Si vous choisissez un pool de plusieurs ordinateurs, entrez les noms des serveurs frontaux individuels de serveur de conversation permanente qui composent le pool.
    
    <div>
    

    > [!IMPORTANT]  
    > Si le rôle serveur de conversation permanente est installé sur un serveur Lync Server&nbsp;2013 Standard Edition, le nom de domaine complet doit correspondre au nom de domaine complet du serveur Standard Edition.

    
    </div>

4.  Définissez un **nom complet** simple pour le pool de serveurs de conversation permanente. Le nom d’affichage peut être utilisé par les clients personnalisés, en particulier lorsqu’il existe plusieurs pools de serveurs de conversation permanente, pour différencier les salles.

5.  Définissez le port utilisé par le serveur de conversation permanente pour communiquer avec les serveurs frontaux Lync Server. Le port par défaut est 5041.

6.  Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**. Si vous choisissez, le service de conformité du serveur de conversation permanente est installé sur le même ordinateur que le serveur frontal du serveur de conversation permanente. Vous êtes invité à sélectionner un serveur principal SQL Server pour la conformité du serveur de conversation permanente par la suite.

7.  Affectez l’affinité de site pour le pool de serveurs de conversation permanente. Activez la case à cocher **utiliser ce pool \<comme\> valeur par défaut pour le site SiteName** ou **Utilisez ce pool par défaut pour tous les sites** pour désigner ce pool de serveurs de conversation permanente comme pool par défaut pour le site actuel ou tous les sites. Lorsque le client Lync 2013 est utilisé pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’expérience de création et de gestion de salle afin de pouvoir acheminer les opérations de création et de gestion de salle vers ce pool. Ceci s’applique uniquement lorsque vous avez déployé plusieurs pools de serveurs de conversation permanente et que vous souhaitez utiliser les fonctionnalités de création et de gestion de salle du serveur de conversation permanente.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez personnaliser les fonctionnalités de création et de gestion de salle à l’aide du kit de développement logiciel (SDK) de serveur de conversation permanente.<BR>Pour plus d’informations sur la configuration des bases de données de sauvegarde SQL Server pour la récupération d’urgence, voir <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

8.  Définissez le **magasin SQL pour le serveur de conversation permanente (où le contenu de la salle de conversation est stocké)** en effectuant l’une des opérations suivantes :
    
      - Pour utiliser une base de données SQL Server existante, dans la liste déroulante, cliquez sur le nom de la base de données SQL Server que vous souhaitez utiliser.
    
      - Pour spécifier une nouvelle base de données SQL Server, cliquez sur **nouveau**, puis dans **définir un nouveau magasin SQL**, effectuez les opérations suivantes :
    
    <!-- end list -->
    
      - Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL Server sur lequel vous voulez créer la nouvelle base de données SQL Server.
    
      - Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.

9.  Définissez la base de données de conformité SQL Server si vous avez activé la conformité.
    
    <div>
    

    > [!IMPORTANT]  
    > Pour plus d’informations sur la configuration des miroirs SQL Server pour la haute disponibilité de la base de données du serveur de conversation permanente et de la base de données de conformité du serveur de conversation permanente, reportez-vous à la rubrique <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

10. Définissez le magasin de fichiers. Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation). Dans le cas d’une topologie de serveur de conversation permanente à plusieurs serveurs, il doit s’agir d’un chemin d’accès UNC (Universal Naming Convention); pour une topologie de serveur de conversation permanente à serveur unique, il peut s’agir d’un chemin d’accès de fichier local.
    
    Pour utiliser un magasin de fichiers existant, procédez ainsi :
    
      - Dans **Nom de domaine complet du serveur de fichiers**, indiquez le nom de domaine complet du magasin de fichiers dans lequel vous voulez créer le nouveau magasin de fichiers.
    
      - Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez définir le magasin de fichiers dans le générateur de topologie avant de créer le magasin de fichiers, mais vous devez créer le magasin de fichiers à l’emplacement défini que vous définissez avant de publier la topologie.

    
    </div>

11. Sélectionnez le pool de serveurs frontaux à utiliser comme tronçon suivant pour ce pool de serveurs de conversation permanente. Il s’agit du pool de serveurs frontaux qui pourra acheminer les demandes de serveur de conversation permanente vers ce pool.

12. Pour enregistrer la configuration, cliquez sur **Terminer**. Le pool de serveurs de conversation permanente apparaît dans le générateur de topologie, accompagné de vos paramètres de pool spécifiques.
    
    Pour publier votre topologie mise à jour sur laquelle vous avez un serveur de conversation permanente, voir [publier la topologie mise à jour dans Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) dans la documentation de déploiement.
    
    <div>
    

    > [!NOTE]  
    > Lorsque le générateur de topologies est déjà ouvert, vous pouvez passer à l’étape 3 de <A href="lync-server-2013-publish-the-updated-topology.md">la publication de la topologie mise à jour dans Lync Server 2013</A> pour commencer à publier votre topologie mise à jour.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

