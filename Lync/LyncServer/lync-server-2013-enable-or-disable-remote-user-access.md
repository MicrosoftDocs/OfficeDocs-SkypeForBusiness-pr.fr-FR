---
title: 'Lync Server 2013 : activation ou désactivation de l’accès des utilisateurs distants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73381280b2d87ff73daa79162571f1f729086b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les utilisateurs distants sont les utilisateurs de votre organisation qui disposent d’une identité Active Directory permanente au sein de l’organisation. Les utilisateurs distants se connectent souvent à Lync Server depuis l’extérieur de votre réseau à l’aide d’un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation. Les utilisateurs distants incluent les employés travaillant à domicile ou sur la route, ainsi que d’autres travailleurs distants, tels que des fournisseurs approuvés, auxquels des informations d’identification d’entreprise ont été accordées. Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent sur Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes à l’aide de Lync Server.

Pour prendre en charge l’accès des utilisateurs distants, vous devez l’activer (pour l’ensemble de votre entreprise). Si vous souhaitez plus tard empêcher temporairement ou définitivement l’accès des utilisateurs distants, vous pouvez le désactiver pour votre entreprise. Suivez la procédure dans cette section pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise.

<div>


> [!NOTE]  
> L’activation de l’accès des utilisateurs distants spécifie que les serveurs exécutant le service Edge d’accès prennent en charge les communications avec des utilisateurs distants, mais que les utilisateurs distants ne peuvent pas participer à la messagerie instantanée ou aux conférences de votre organisation jusqu’à ce que vous configuriez également moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet. Pour plus d’informations sur la configuration des stratégies pour l’utilisation de l’accès des utilisateurs distants, voir <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe **, puis sur **Configuration du serveur Edge d’accès**.

4.  Sur la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs distants pour votre entreprise, activez la case à cocher **Activer l’accès des utilisateurs distants**.
    
      - Pour désactiver l’accès des utilisateurs distants pour votre entreprise, désactivez la case à cocher **Activer l’accès des utilisateurs distants**.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs distants de se connecter à vos serveurs exécutant Lync Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants. Pour plus d’informations, voir [configure Policies to Control Remote User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) dans la documentation de déploiement ou la documentation des opérations.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès des utilisateurs distants à l’aide des applets de commande Windows PowerShell

L’accès des utilisateurs distants peut être géré à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-enable-remote-user-access"></a>Pour activer l’accès des utilisateurs distants

  - Pour activer l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Pour désactiver l’accès des utilisateurs distants

  - Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers ** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

