---
title: 'Lync Server 2013 : Définition des topologies facultatives de directeur dans votre topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Définition des topologies facultatives de directeur dans votre topologie pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

Les directeurs Lync Server 2013 peuvent être des serveurs à instance unique qui peuvent être installés en tant que pool équilibré en charge de plusieurs directeurs pour une disponibilité et une capacité plus élevées. L’équilibrage de charge matérielle et l’équilibrage de charge DNS (Domain Name System) sont pris en charge. Cet article explique comment configurer l’équilibrage de charge DNS pour les pools de directeurs.

Pour réussir la publication, l’activation ou la désactivation d’une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes **RTCUniversalServerAdmins** et **Admins du domaine** . Vous pouvez également déléguer les droits d’administrateur et les autorisations appropriés pour ajouter des rôles de serveur. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement Standard Edition Server ou Enterprise Edition Server. Pour les autres modifications de configuration, seule l’appartenance au groupe **RTCUniversalServerAdmins** est requise.

Cette rubrique décrit les étapes permettant de définir et de publier la topologie pour les deux topologies de Director:

  - Pour définir le directeur (instance unique)

  - Pour définir le directeur (pool de directeurs multiples)

<div>

## <a name="to-define-the-director-single-instance"></a>Pour définir le directeur (instance unique)

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans la page Bienvenue, cliquez sur **Télécharger la topologie à partir du déploiement existant**.

3.  Dans la boîte de dialogue **enregistrer la topologie en tant que** , entrez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer**.

4.  Développez le site dans lequel vous envisagez d’ajouter le directeur, **** cliquez avec le bouton droit sur pools de réalisateurs, puis cliquez sur **nouvelle liste de répertoires**.

5.  Dans la boîte de dialogue **définir le nom de domaine complet du pool** de répertoires, procédez comme suit:
    
      - Dans **nom de domaine complet (FQDN**) du pool, tapez le nom de domaine complet (FQDN) du pool
    
      - Cliquez sur **pool d’ordinateurs unique**, puis sur **suivant**.

6.  Dans la boîte de dialogue **définir le partage de fichiers** , effectuez l’une des opérations suivantes:
    
    1.  Pour utiliser un partage de fichier existant, cliquez sur **utiliser un partage de fichiers déjà défini**, sélectionnez un partage de fichiers dans la liste, puis cliquez sur **suivant**.
    
    2.  Pour créer un nouveau partage de fichiers, cliquez sur **définir un nouveau partage de fichier**, tapez le nom de domaine complet (FQDN) de l’emplacement du partage de fichiers dans **nom de domaine complet du serveur de fichiers**, tapez le nom du partage dans partage de **fichiers**, puis cliquez sur **suivant**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le partage de fichiers que vous spécifiez ou créez dans cette étape doit exister ou être créé avant la publication de la topologie.<BR>Le partage de fichiers attribué à un directeur n’est pas utilisé pour vous permettre d’affecter le partage de fichiers de n’importe quel pool au sein de l’organisation.

    
    </div>

7.  Dans la boîte de dialogue **spécifier l’URL du service Web** , dans **URL de base externe**, spécifiez le nom de domaine complet (FQDN) pour les directeurs, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le nom doit pouvoir être résolu à partir des serveurs DNS Internet et pointe vers l’adresse IP publique du proxy inverse, qui écoute les demandes HTTP/HTTPs à cette URL et les transmet au répertoire virtuel des services Web externes de ce réalisateur.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateur.

    
    </div>

8.  Publiez la topologie.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Pour définir le directeur (pool de directeurs multiples)

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans la page Bienvenue, cliquez sur **Télécharger la topologie à partir du déploiement existant**.

3.  Dans la boîte de dialogue **enregistrer la topologie en tant que** , entrez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer**.

4.  Développez le site dans lequel vous envisagez d’ajouter le directeur, **** cliquez avec le bouton droit sur pools de réalisateurs, puis cliquez sur **nouvelle liste de répertoires**.

5.  Dans la boîte de dialogue **définir le nom de domaine complet du pool** de répertoires, procédez comme suit:
    
      - Dans **nom de domaine complet (FQDN**) du pool, tapez le nom de domaine complet (FQDN) du pool
    
      - Cliquez sur **plusieurs pools d’ordinateurs**, puis cliquez sur **suivant**.

6.  Dans la boîte de dialogue **définir les ordinateurs dans cette liste** , procédez comme suit:
    
      - Spécifiez le nom de domaine complet du premier membre de la liste, puis cliquez sur **Ajouter**.
    
      - Répétez l’étape précédente pour chaque ordinateur que vous voulez ajouter. Lorsque vous avez terminé, cliquez sur **suivant**.

7.  Dans la boîte de dialogue **définir le partage de fichiers** , effectuez l’une des opérations suivantes:
    
      - Pour utiliser un partage de fichier existant, cliquez sur **utiliser un partage de fichiers déjà défini**, sélectionnez un partage de fichiers dans la liste, puis cliquez sur **suivant**.
    
      - Pour créer un nouveau partage de fichiers, cliquez sur **définir un nouveau partage de fichier**, tapez le nom de domaine complet (FQDN) de l’emplacement du partage de fichiers dans **nom de domaine complet du serveur de fichiers**, tapez le nom du partage dans partage de **fichiers**, puis cliquez sur **suivant**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le partage de fichiers que vous spécifiez ou créez dans cette étape doit exister ou être créé avant la publication de la topologie.<BR>Le partage de fichiers attribué à un directeur n’est pas utilisé pour vous permettre d’affecter le partage de fichiers de n’importe quel pool au sein de l’organisation.

    
    </div>

8.  Dans la boîte de dialogue **spécifier l’URL du service Web** , dans **URL de base externe**, spécifiez le nom de domaine complet (FQDN) pour les directeurs, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Ce nom ne doit pas être résolu à partir des serveurs DNS Internet et pointe vers l’adresse IP publique du proxy inverse, qui écoute les requêtes HTTP/HTTPs envoyées à cette URL et les transmet au répertoire virtuel des services Web externes dans ce pool de répertoires.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateur.

    
    </div>

9.  Publiez la topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

