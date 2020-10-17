---
title: Modification des URL simples après la migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029fe44d33d41b410d23068551203b1532893354
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499691"
---
# <a name="change-simple-urls-after-migration"></a>Modification des URL simples après la migration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Lync Server prend en charge trois URL simples :

  - **Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation. Avec l’URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre, à communiquer et à distribuer.

  - **Dial-in** qui permet d’accéder à la page web Paramètres de conférence rendez-vous. L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.

  - L' **administrateur** permet un accès rapide au panneau de configuration Lync Server. L’URL simple d’administration est interne à votre organisation.

Après avoir effectué la migration vers Lync Server 2013, vous devez savoir comment la modification influe sur vos enregistrements DNS et les certificats pour les URL simples. Si le directeur Lync Server 2010 hérité reste utilisé dans la topologie, aucune modification de vos URL simples n’est requise. Si le directeur Lync Server 2010 est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour pour pointer vers l’un des pools Lync Server 2013. Cependant, lorsque vous modifiez le nom d’une URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et serveur frontal pour enregistrer la modification.

<div>

## <a name="changing-simple-urls-after-migration"></a>Modification des URL simples après la migration

**Pour mettre à jour l’URL simple Meet**

1.  Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.

2.  Sélectionnez **URL simples** dans le volet de gauche, puis sous URL de la **réunion :** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.

3.  Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer.

**Pour mettre à jour l’URL simple Admin**

1.  Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.

2.  Sélectionnez **URL simples** dans le volet gauche, en dessous de zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour l’accès administratif au panneau de configuration Lync Server 2013, puis cliquez sur **OK**.
    
    <div>
    

    > [!TIP]  
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin. L’option la plus simple est <STRONG> https://admin .</STRONG> &lt; domaine &gt; .

    
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

