---
title: 'Lync Server 2013 : configuration de la prise en charge des domaines externes bloqués'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f24c7db21daa02ff67dc8eb4ddf375c78f96b6d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configurer la prise en charge des domaines externes bloqués dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines qui n’auront pas accès à la fédération au sein de votre organisation. La liste des domaines bloqués sert de liste rouge (liste d’entrées explicites qui doivent être interdites) et s’applique à la découverte des domaines fédérés, si cette option est activée. Pour plus d’informations, consultez la rubrique [activation ou désactivation de la découverte de partenaires de Fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Empêchez un ou plusieurs domaines externes de se connecter à votre organisation. Pour ce faire, ajoutez le domaine à la liste des domaines bloqués.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Pour ajouter un domaine externe à la liste des domaines bloqués

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**.

4.  Cliquez sur **Domaines fédérés**, sur **Nouveau**, puis sur **Domaine bloqué**.

5.  Dans **Nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **Nom de domaine complet (ou FQDN)**, tapez le nom de domaine du partenaire fédéré que vous souhaitez bloquer.
        
        <div>
        

        > [!NOTE]  
        > Il peut contenir jusqu’à 256 caractères.<BR>La recherche du nom de domaine du partenaire fédéré établit une correspondance à partir du suffixe. Par exemple, si vous tapez <STRONG>contoso.com</STRONG>, la recherche renverra également le domaine <STRONG>it.contoso.com</STRONG>.<BR>Un domaine de partenaire fédéré ne peut pas être simultanément bloqué et autorisé. Lync Server 2013 empêche ce problème de se produire afin que vous n’ayez pas besoin de synchroniser vos listes.

        
        </div>
    
      - (Facultatif) Dans **Commentaire**, tapez les informations sur cette configuration que vous voulez partager avec les autres administrateurs système.

6.  Cliquez sur **Valider**.

7.  Répétez les étapes 4 à 6 pour chaque partenaire fédéré que vous souhaitez bloquer.

Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de l’accès des utilisateurs fédérés dans votre organisation. Pour plus d’informations, consultez la rubrique [activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

De plus, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés. Pour plus d’informations, consultez la rubrique [configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

