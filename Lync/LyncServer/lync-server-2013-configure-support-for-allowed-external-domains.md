---
title: 'Lync Server 2013 : Configuraton de la prise en charge des domaines externes autorisés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31aa2ab9db9ffccd3acda90e9651dfad20b85e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines spécifiques qu’il est possible de fédérer avec votre organisation. Vous pouvez configurer un ou plusieurs domaines externes spécifiques en tant que domaines fédérés autorisés. Pour ce faire, ajoutez chaque domaine à la liste des domaines autorisés. Même si la découverte des partenaires est activée pour votre organisation, procédez comme suit si le domaine est un partenaire fédéré qui peut avoir besoin de communiquer avec plus de 1 000 ou si vous avez besoin d’envoyer plus de 20 messages par seconde. Si la découverte de partenaire n’est pas activée pour votre organisation, seuls les utilisateurs de domaines externes que vous ajoutez à la liste des domaines autorisés peuvent participer à la messagerie instantanée et à la Conférence avec les utilisateurs de votre organisation. Si vous souhaitez limiter l’accès d’un domaine fédéré à un serveur spécifique exécutant le service Edge d’accès du partenaire fédéré, vous pouvez spécifier le nom de domaine du serveur exécutant le service Edge d’accès pour chaque domaine dans la liste des domaines autorisés.

<div>


> [!NOTE]  
> Cette procédure vous explique comment configurer la prise en charge des domaines spécifiques, mais que l’implémentation de la prise en charge des utilisateurs fédérés nécessite également l’activation de la prise en charge des utilisateurs fédérés pour votre organisation et la configuration et l’application de stratégies pour contrôler les utilisateurs qui peuvent collaborer avec des utilisateurs fédérés. Pour plus d’informations sur l’activation de la prise en charge des utilisateurs fédérés, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</A>. Pour plus d’informations sur la configuration des stratégies pour contrôler la Fédération, voir <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Pour ajouter un domaine externe à la liste des domaines autorisés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **domaines fédérés**.

4.  Sur la page **domaines fédérés** , cliquez sur **nouveau**, puis cliquez sur **domaine autorisé**.

5.  Dans **nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **nom de domaine (ou nom de domaine complet)**, tapez le nom du domaine du partenaire fédéré.
        
        <div>
        

        > [!NOTE]  
        > Ce nom doit être unique et ne peut pas déjà exister en tant que domaine autorisé pour ce serveur exécutant le service Edge d’accès. Le nom ne peut pas contenir plus de 256 caractères.<BR>La recherche du nom de domaine du partenaire fédéré effectue une correspondance de suffixe. Par exemple, si vous tapez <STRONG>contoso.com</STRONG>, la recherche renverra également le domaine <STRONG>it.contoso.com</STRONG>.<BR>Un domaine de partenaire fédéré ne peut pas être bloqué et autorisé simultanément. Lync Server 2013 empêche cela d’avoir lieu de sorte que vous n’ayez pas à synchroniser vos listes.

        
        </div>
    
      - Si vous voulez limiter l’accès à ce domaine fédéré aux utilisateurs d’un serveur spécifique exécutant le service Edge d’accès (FQDN), tapez le nom de domaine complet **(FQDN)** du serveur du domaine fédéré exécutant le service Edge d’accès.
    
      - Si vous voulez fournir des informations supplémentaires, dans **commenter**, tapez les informations que vous voulez partager avec d’autres administrateurs système sur cette configuration.

6.  Cliquez sur **Valider**.

7.  Répétez les étapes 4 à 6 pour chaque domaine partenaire fédéré que vous souhaitez autoriser.

Pour autoriser l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de l’accès des utilisateurs fédérés au sein de votre organisation. Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Par ailleurs, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez pouvoir collaborer avec des utilisateurs fédérés. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

