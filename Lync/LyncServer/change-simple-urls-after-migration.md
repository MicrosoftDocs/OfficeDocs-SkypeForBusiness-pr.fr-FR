---
title: Modification des URL simples après la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0203b33d787310544f4f376872ecf9c99fc7254d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Modification des URL simples après la migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-22_

Lync Server prend en charge trois URL simples:

  - La **fonction réunion** est utilisée comme URL de base pour toutes les conférences du site ou de l’organisation. Avec l’URL de la réunion, vous pouvez facilement comprendre les liens permettant de participer à des réunions, et facilement communiquer et diffuser.

  - Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous. L’URL d’accès à un rendez-vous est incluse dans toutes les invitations à une réunion de sorte que les utilisateurs qui souhaitent se connecter à la réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.

  - L' **administrateur** vous permet d’accéder rapidement au panneau de configuration de Lync Server. L’URL simple Admin est interne à votre organisation.

Après avoir effectué la migration vers Lync Server 2013, vous devez tenir compte de la façon dont le changement a un impact sur vos enregistrements et certificats DNS pour des URL simples. Si le réalisateur du serveur Lync Server 2010 hérité reste en cours d’utilisation dans la topologie, aucune modification de vos URL simples n’est requise. Si le directeur de Lync Server 2010 est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour de manière à ce qu’ils pointent vers l’une des listes 2013 du serveur Lync. Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque réalisateur et serveur frontal pour enregistrer la modification.

<div>

## <a name="changing-simple-urls-after-migration"></a>Modification d’URL simples après la migration

**Pour mettre à jour l’URL de réunion simple**

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.

2.  Sélectionnez **URL simples** dans le volet gauche, puis sous **URL de la réunion:** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.

3.  Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée.

**Pour mettre à jour l’URL simple d’administration**

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.

2.  Sélectionnez **URL simples** dans le volet gauche, puis sous **URL d’accès administratif** , entrez l’URL de votre choix pour l’accès administratif à Lync Server 2013 panneau de configuration, puis cliquez sur **OK**.
    
    <div>
    

    > [!TIP]  
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration. L’option la plus simple est <STRONG> https://admin.</STRONG> &lt;Domain&gt;(domaine).

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

