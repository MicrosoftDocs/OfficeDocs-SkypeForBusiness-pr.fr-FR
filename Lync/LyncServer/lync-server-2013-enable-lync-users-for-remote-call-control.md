---
title: 'Lync Server 2013 : activation des utilisateurs Lync pour le contrôle d’appel distant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baa6f18e92eb284cce8610ba576b30dd6d2f320
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Vous pouvez configurer des utilisateurs Lync pour le contrôle d’appel distant à l’aide de stratégies de mise en service intrabande basées sur un serveur. Vous pouvez gérer les paramètres de mise en service intrabande à l’aide du panneau de configuration Lync Server ou de l’interface de ligne de commande Lync Server Management Shell. Ces outils remplacent le composant logiciel enfichable WMI (Windows Management Instrumentation) qui a été utilisé pour gérer les paramètres de stratégie de groupe dans les versions antérieures.

Si vous préférez permettre aux utilisateurs de configurer leurs propres paramètres de contrôle d’appel distant dans Lync, vous pouvez configurer les paramètres de contrôle d’appel distant pour les utilisateurs sur le serveur sans spécifier les valeurs URI de ligne de **serveur** et URI de **ligne** . Assurez-vous de communiquer les valeurs URI de **ligne** et URI de **serveur de ligne** appropriées à vos utilisateurs, et fournissez à vos utilisateurs les instructions permettant de configurer ces paramètres. Pour connaître la procédure permettant de configurer manuellement le contrôle d’appel distant dans Lync Server, voir « définition des options <http://go.microsoft.com/fwlink/p/?linkid=210132> et des numéros de téléphone » dans la documentation du client Lync sur le site Web de Microsoft Office.

Si vous disposez d’un déploiement de Communications Server 2007 R2 ou Communications Server 2007 existant, les clients Communicator 2007 R2 et Communicator 2007 continueront à utiliser la stratégie de groupe lors de la migration côte à côte. Toutefois, si vous souhaitez que les paramètres de stratégie soient transférés vers les clients Lync, vous devez configurer les paramètres de mise en service intrabande Lync Server équivalents.

<div>


> [!NOTE]  
> Pour activer un utilisateur pour le contrôle d’appel distant, vous devez fournir à l’utilisateur un URI de ligne et un URI de serveur de ligne. Comme décrit dans <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tâches de déploiement pour le contrôle d’appel distant dans Lync Server 2013</A>, vous devez être sûr d’utiliser la syntaxe requise par la passerelle pour ces paramètres.<BR>Assurez-vous que le domaine dans l’URI du serveur de ligne est identique au domaine de destination spécifié dans le paramètre MatchUri lors de la configuration de l’itinéraire statique vers la passerelle.<BR>L’URI de ligne spécifie le numéro de téléphone affecté à l’utilisateur au format E. 164, avec le préfixe « TEL : » (par exemple, Tél : + 14255550150). Si vous souhaitez configurer un numéro de poste, le format est Tél. : + 14255550150 ; ext = 111. Si vous avez configuré précédemment l’URI de ligne de l’utilisateur et que la valeur n’a pas changé, vous n’avez pas besoin de spécifier l’URI de ligne lorsque vous activez l’utilisateur pour le contrôle d’appel distant.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Pour activer le contrôle d’appel distant pour les utilisateurs à extension Lync à l’aide de Management Shell

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou en tant que rôle de contrôle d’accès basé sur un rôle auquel vous avez affecté la cmdlet **Set-Csuser** .

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Pour utiliser la cmdlet **Set-Csuser** afin de configurer le contrôle d’appel distant pour un utilisateur compatible Lync existant, procédez comme suit :
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Par exemple :
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Pour configurer les utilisateurs pour le contrôle d’appel distant à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs** , tapez tout (ou la première partie) du nom d’affichage, du prénom, du nom de famille, du nom de compte Sam (Security Accounts Manager), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne de votre choix, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.

6.  Dans le menu **Edition**, cliquez sur **Modifier**.

7.  Dans **téléphonie**, effectuez l’une des opérations suivantes :
    
      - Pour activer le contrôle d’appel distant afin de permettre à l’utilisateur de contrôler son téléphone PBX (Private Branch Exchange) à partir de Lync 2013 afin de passer des appels audio PC à PC et des appels PC à téléphone, cliquez sur **contrôle d’appel distant**. Dans **URI de ligne**, spécifiez le numéro de téléphone de l’utilisateur. Dans **URI du serveur de ligne**, spécifiez l’URI SIP de la passerelle SIP/CSTA.
    
      - Pour activer le contrôle d’appel distant, mais désactiver les appels audio de PC à PC et permettre uniquement à l’utilisateur de contrôler son téléphone PBX à partir de Lync 2013 pour effectuer des appels PC à téléphone, cliquez sur **contrôle d’appel distant uniquement**. Dans **URI de ligne**, spécifiez le numéro de téléphone de l’utilisateur. Dans **URI du serveur de ligne**, spécifiez l’URI SIP de la passerelle SIP/CSTA.

8.  Lorsque vous avez terminé, cliquez sur **valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

