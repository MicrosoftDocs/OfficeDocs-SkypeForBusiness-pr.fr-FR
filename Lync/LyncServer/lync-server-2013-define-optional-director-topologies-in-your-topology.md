---
title: 'Lync Server 2013 : définition de topologies facultatives de directeur dans votre topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0448ddfdb9988b791ff14dff89ab4c122df1d38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Définir des topologies facultatives de directeur dans votre topologie pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Les directeurs Lync Server 2013 peuvent être des serveurs à instance unique ou être installés en tant que pool à charge équilibrée de plusieurs directeurs pour une disponibilité et une capacité supérieures. L’équilibrage de la charge matérielle et de la charge DNS sont tous deux pris en charge. Cette rubrique explique comment configurer l’équilibrage de la charge DNS pour les pools directeurs.

Pour réussir à publier, activer ou désactiver une topologie lorsque vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes **RTCUniversalServerAdmins** et **Domain Admins**. Il est également possible de déléguer les droits et les autorisations d’administrateur appropriés pour ajouter des rôles serveur. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement du serveur Standard Edition Server ou Enterprise Edition. En ce qui concerne les autres modifications de configuration, seule l’appartenance au groupe **RTCUniversalServerAdmins** est requise.

Cette rubrique décrit les étapes à suivre pour définir et publier la topologie pour les deux topologies de directeur :

  - Pour définir le directeur (instance unique)

  - Pour définir le directeur (pool de plusieurs directeurs)

<div>

## <a name="to-define-the-director-single-instance"></a>Pour définir le directeur (instance unique)

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans la page d’accueil, cliquez sur **Télécharger la topologie à partir du déploiement existant**.

3.  Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer**.

4.  Développez le site dans lequel vous planifiez d’ajouter le directeur , cliquez avec le bouton droit sur **Pools directeurs**, puis cliquez sur **Nouveau pool directeur**.

5.  Dans la boîte de dialogue **Définir le nom de domaine complet du pool directeur**, procédez comme suit :
    
      - Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet du pool directeur.
    
      - Cliquez sur **Pool d’un seul ordinateur**, puis sur **Suivant**.

6.  Dans la boîte de dialogue **Définir le partage de fichiers**, effectuez l’une des opérations suivantes :
    
    1.  Pour utiliser un partage de fichiers existant, cliquez sur **Utiliser un partage de fichiers précédemment défini**, sélectionnez un partage de fichiers dans la liste, puis cliquez sur **Suivant**.
    
    2.  Pour créer un partage de fichiers, cliquez sur **Définir un nouveau partage de fichiers**, tapez le nom de domaine complet de l’emplacement du partage de fichiers dans **Nom de domaine complet du serveur de fichiers**, tapez le nom du partage dans **Partage de fichiers**, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le partage de fichiers que vous spécifiez ou créez à cette étape doit exister ou être créé avant de publier la topologie.<BR>Le partage de fichiers attribué à un directeur n’est pas utilisé, si bien que vous pouvez attribuer le partage de fichiers de n’importe quel pool dans l’entreprise.

    
    </div>

7.  Dans la boîte de dialogue **Spécifier l’URL des services Web**, dans **URL de base externe**, spécifiez le nom de domaine complet des directeurs, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le nom doit pouvoir être résolu à partir des serveurs DNS Internet et doit pointer vers l’adresse IP publique du proxy inverse. Celui-ci écoute les demandes HTTP/HTTPS envoyées à cette URL et les transmet via le serveur proxy au répertoire virtuel des services web externes sur ce directeur.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.

    
    </div>

8.  Publiez la topologie.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Pour définir le directeur (pool de plusieurs directeurs)

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans la page d’accueil, cliquez sur **Télécharger la topologie à partir du déploiement existant**.

3.  Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer**.

4.  Développez le site dans lequel vous planifiez d’ajouter le directeur , cliquez avec le bouton droit sur **Pools directeurs**, puis cliquez sur **Nouveau pool directeur**.

5.  Dans la boîte de dialogue **Définir le nom de domaine complet du pool directeur**, procédez comme suit :
    
      - Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet du pool directeur.
    
      - Cliquez sur **Pool de plusieurs ordinateurs**, puis sur **Suivant**.

6.  Dans la boîte de dialogue **Définissez les ordinateurs inclus dans ce pool**, procédez comme suit :
    
      - Spécifiez le nom de domaine complet d’ordinateur du premier membre du pool, puis cliquez sur **Ajouter**.
    
      - Répétez l’étape précédente pour chaque ordinateur à ajouter. Lorsque vous avez terminé, cliquez sur **Suivant**.

7.  Dans la boîte de dialogue **Définir le partage de fichiers**, effectuez l’une des opérations suivantes :
    
      - Pour utiliser un partage de fichiers existant, cliquez sur **Utiliser un partage de fichiers précédemment défini**, sélectionnez un partage de fichiers dans la liste, puis cliquez sur **Suivant**.
    
      - Pour créer un partage de fichiers, cliquez sur **Définir un nouveau partage de fichiers**, tapez le nom de domaine complet de l’emplacement du partage de fichiers dans **Nom de domaine complet du serveur de fichiers**, tapez le nom du partage dans **Partage de fichiers**, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le partage de fichiers que vous spécifiez ou créez à cette étape doit exister ou être créé avant de publier la topologie.<BR>Le partage de fichiers attribué à un directeur n’est pas utilisé, si bien que vous pouvez attribuer le partage de fichiers de n’importe quel pool dans l’entreprise.

    
    </div>

8.  Dans la boîte de dialogue **Spécifier l’URL des services Web**, dans **URL de base externe**, spécifiez le nom de domaine complet des directeurs, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le nom doit pouvoir être résolu à partir des serveurs DNS Internet et doit pointer vers l’adresse IP publique du proxy inverse. Celui-ci écoute les demandes HTTP/HTTPS envoyées à cette URL et les redirige via proxy au répertoire virtuel des services Web externes sur ce pool directeur.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.

    
    </div>

9.  Publiez la topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

