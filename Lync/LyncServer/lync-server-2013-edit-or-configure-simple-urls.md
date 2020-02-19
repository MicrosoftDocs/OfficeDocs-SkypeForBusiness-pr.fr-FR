---
title: 'Lync Server 2013 : modifier ou configurer des URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1618ca331b66612051b2a824aa5ebd2adfac043a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Modifier ou configurer des URL simples dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

Pour effectuer cette procédure, il n’est pas nécessaire d’appartenir à un groupe d’administrateurs local ou de domaines privilégiés. Vous devez simplement ouvrir une session sur un ordinateur en tant qu’utilisateur standard.

Lync Server 2013 utilise des URL simples pour diriger les appels internes et externes vers des services sur le serveur frontal ou sur le directeur, le cas échéant. Pour plus d’informations sur les URL simples, voir [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) dans la documentation de planification. Vous pouvez sélectionner le format de vos URL simples à partir de plusieurs options. Pour plus d’informations sur ces options, consultez la rubrique [DNS Requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) dans la documentation de planification.

Par défaut, les URL simples sont configurées sous la forme (par exemple, l’URL simple Dial-in) : https://dialin.\<SIP Domain.\>

<div>

## <a name="to-configure-simple-urls"></a>Pour configurer des URL simples

1.  Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud **Lync Server** , puis cliquez sur **modifier les propriétés**.

2.  Dans le volet **URL simples** , sélectionnez **URL d’accès téléphonique :** (accès à distance) ou **URL de réunion :** (réunion) pour modifier, puis cliquez sur **modifier l’URL**.

3.  Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer. L’exemple ci-dessous a modifié l’URL de connexion vers https://pool01.contoso.net/dialin.

4.  Modifiez l’URL Meet en procédant de la même manière, si nécessaire.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Pour définir l’URL simple Admin facultative

1.  Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud **Lync Server** , puis cliquez sur **modifier les propriétés**.

2.  Dans la zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour l’accès administratif au panneau de configuration Lync Server 2013, puis cliquez sur **OK**.
    
    <div>
    

    > [!TIP]  
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin. L’option la plus simple est <STRONG> https://admin.</STRONG> &lt;domaine&gt;.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous modifiez une URL simple après le déploiement initial, vous devez savoir quelles modifications ont un impact sur les enregistrements DNS (Domain Name System) et les certificats pour les URL simples. Si la modification a un impact sur la base d’une URL simple, vous devez également modifier les enregistrements DNS et les certificats. Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com en Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com. Si vous avez modifié l’URL simple https://lync.contoso.com/Meet vers https://lync.contoso.com/Meetings, l’url de base de Lync.contoso.com reste la même, de sorte qu’aucune modification de certificat ou de DNS n’est nécessaire. Chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter l’applet de commande <STRONG>Enable-CsComputer</STRONG> sur chaque directeur et serveur frontal pour enregistrer la modification.

    
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

