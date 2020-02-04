---
title: 'Lync Server 2013 : Modification ou configuration des URL simples'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Modification ou configuration des URL simples dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

Cette procédure ne nécessite pas d’appartenance à un administrateur local ou à un groupe de domaines privilégiés. Vous devez vous connecter à un ordinateur en tant qu’utilisateur standard.

Lync Server 2013 utilise des URL simples pour diriger les appels internes et externes vers des services du serveur frontal ou du réalisateur, s’il a été déployé. Pour plus d’informations sur les URL simples, voir [planification d’URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) dans la documentation de planification. Vous pouvez sélectionner le format de vos URL simples à partir de plusieurs options. Pour plus d’informations sur ces options, voir [configurations DNS requises pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) dans la documentation de planification.

Par défaut, les URL simples seront configurées sous la forme (par exemple, l’URL de connexion simple) : https://dialin.\<SIP Domain\>

<div>

## <a name="to-configure-simple-urls"></a>Pour configurer des URL simples

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud du **serveur Lync** , puis cliquez sur **modifier les propriétés**.

2.  Dans le volet **URL simples**, sélectionnez **URL d’accès téléphonique :** (Dial-In) ou **URL de réunion :** (Meet) pour modifier l’URL, puis cliquez sur **Modifier l’URL**.

3.  Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée. L’exemple présenté ici a modifié l’URL d’accès à la https://pool01.contoso.net/dialinConférence rendez-vous en.

4.  Modifiez l’URL Meet en procédant de la même manière, si nécessaire.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Pour définir l’URL simple Admin facultative

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud du **serveur Lync** , puis cliquez sur **modifier les propriétés**.

2.  Dans la zone **URL d’accès administratif** , entrez l’URL de votre choix pour l’accès administratif au panneau de configuration de Lync Server 2013, puis cliquez sur **OK**.
    
    <div>
    

    > [!TIP]  
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration. L’option la plus simple est <STRONG> https://admin.</STRONG> &lt;Domain&gt;(domaine).

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous changez une URL simple après son déploiement initial, vous devez savoir quels changements impactent vos enregistrements et certificats DNS pour les URL simples. Si le changement a un impact sur la base d’une URL simple, vous devez également modifier les enregistrements DNS et les certificats. Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com à Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com. Si vous avez changé l’URL simple https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingsà, l’url de base de Lync.contoso.com reste inchangée et aucune modification du DNS ou du certificat n’est nécessaire. Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter l’applet de passe <STRONG>Enable-CsComputer</STRONG> sur chaque réalisateur et serveur frontal pour enregistrer la modification.

    
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

