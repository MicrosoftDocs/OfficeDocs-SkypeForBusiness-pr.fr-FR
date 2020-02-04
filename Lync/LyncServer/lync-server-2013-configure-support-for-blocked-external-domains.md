---
title: 'Lync Server 2013 : Configuration de la prise en charge pour les domaines externes bloqués'
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
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configuration de la prise en charge pour les domaines externes bloqués dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines qui seront bloqués par votre organisation. Si cette option est activée, la liste des domaines bloqués fera office de liste de blocage (liste d’entrées explicites qui ne seront pas autorisées) et sera appliquée dans découverte de domaine fédéré. Pour plus d’informations, voir [activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Bloquer un ou plusieurs domaines externes pour vous connecter à votre organisation. Pour ce faire, ajoutez le domaine à la liste des domaines bloqués.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Pour ajouter un domaine externe à la liste des domaines bloqués

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès des utilisateurs externes**.

4.  Cliquez sur **domaines fédérés**, sur **nouveau**, puis sur **domaine bloqué**.

5.  Dans **nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **nom de domaine (ou nom de domaine complet)**, tapez le nom du domaine de partenaire fédéré que vous souhaitez bloquer.
        
        <div>
        

        > [!NOTE]  
        > Le nom ne peut pas contenir plus de 256 caractères.<BR>La recherche du nom de domaine du partenaire fédéré effectue une correspondance de suffixe. Par exemple, si vous tapez <STRONG>contoso.com</STRONG>, la recherche renverra également le domaine <STRONG>it.contoso.com</STRONG>.<BR>Un domaine de partenaire fédéré ne peut pas être bloqué et autorisé simultanément. Lync Server 2013 empêche cela d’avoir lieu de sorte que vous n’ayez pas à synchroniser vos listes.

        
        </div>
    
      - Facultatif Dans **Commentaire**, tapez les informations que vous voulez partager avec d’autres administrateurs système sur cette configuration.

6.  Cliquez sur **Valider**.

7.  Répétez les étapes 4 à 6 pour chaque partenaire fédéré que vous souhaitez bloquer.

Pour autoriser l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de l’accès des utilisateurs fédérés au sein de votre organisation. Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Par ailleurs, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez pouvoir collaborer avec des utilisateurs fédérés. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

