---
title: 'Lync Server 2013 : Activation ou désactivation de l’accès des utilisateurs distants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Les utilisateurs distants sont les utilisateurs de votre organisation qui ont une identité Active Directory persistante au sein de l’organisation. Les utilisateurs distants se connectent souvent à Lync Server depuis l’extérieur de votre réseau via un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation. Les utilisateurs distants incluent des employés travaillant à la maison ou en déplacement, ainsi que d’autres travailleurs distants, tels que des fournisseurs approuvés qui ont reçu des informations d’identification d’entreprise. Si vous autorisez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes de Lync Server.

Pour prendre en charge l’accès des utilisateurs distants, vous devez activer l’accès des utilisateurs distants. Lorsque vous activez l’accès des utilisateurs distants, vous les activez pour l’ensemble de votre organisation. Si vous souhaitez empêcher l’accès des utilisateurs distants de manière temporaire ou définitive, vous pouvez le désactiver pour votre organisation. Suivez la procédure décrite dans cette section pour activer ou désactiver l’accès des utilisateurs distants au sein de votre organisation.

<div>


> [!NOTE]  
> L’activation de l’accès des utilisateurs distants indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge les communications avec les utilisateurs distants, mais qu’ils ne peuvent pas participer à la messagerie instantanée ou aux conférences au sein de votre organisation tant que vous n’avez pas également configuré au moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants. Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de serveur Lync est défini comme suit: la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet. Pour plus d’informations sur la configuration des stratégies pour l’utilisation de l’accès des utilisateurs distants, voir <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs distants pour votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.

5.  Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes:
    
      - Pour autoriser l’accès des utilisateurs distants pour votre organisation, activez la case à cocher **activer l’accès aux utilisateurs** distants.
    
      - Pour désactiver l’accès des utilisateurs distants pour votre organisation, décochez la case **activer l’accès distant aux utilisateurs** .

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs distants de se connecter à des serveurs exécutant Lync Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) dans la documentation de déploiement ou la documentation des opérations.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès des utilisateurs distants à l’aide d’applets de commande Windows PowerShell

L’accès des utilisateurs distants peut être géré à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-enable-remote-user-access"></a>Pour autoriser l’accès des utilisateurs distants

  - Pour autoriser l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Pour désactiver l’accès des utilisateurs distants

  - Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur false ($false):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

