---
title: 'Lync Server 2013 : Activation des utilisateurs Lync pour le contrôle d’appel distant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Vous pouvez configurer les utilisateurs de Lync pour le contrôle d’appel distant à l’aide de stratégies d’approvisionnement intrabande basées sur le serveur. Vous pouvez gérer les paramètres de mise en service intrabande à l’aide du panneau de configuration de Lync Server ou de l’interface de ligne de commande de Lync Server Management Shell. Ces outils remplacent le composant logiciel enfichable WMI (Windows Management Instrumentation) utilisé pour gérer les paramètres de stratégie de groupe dans les versions précédentes.

Si vous préférez permettre aux utilisateurs de configurer leur propre paramètre de contrôle d’appel distant dans Lync, vous pouvez configurer les paramètres de contrôle des appels distants pour les utilisateurs sur le serveur sans spécifier les valeurs **URI de ligne** et URI de **ligne** . Assurez-vous de communiquer les **** valeurs URI de ligne **** et URI de ligne appropriées à vos utilisateurs, puis fournissez aux utilisateurs les instructions de configuration de ces paramètres. Pour la procédure de configuration manuelle du contrôle d’appel distant dans Lync Server, voir la section «définir les options <http://go.microsoft.com/fwlink/p/?linkid=210132> et les numéros de téléphone» dans la documentation du client Lync sur le site Web Microsoft Office.

Si vous disposez d’un déploiement de 2007 Communications Server 2007 R2 ou Communications Server, les clients Communicator 2007 R2 et Office Communicator 2007 continuent d’utiliser une stratégie de groupe pendant la migration côte à côte. Toutefois, si vous voulez que les paramètres de stratégie soient transférés aux clients Lync, vous devez configurer les paramètres de mise en service de Lync Server in-Band correspondants.

<div>


> [!NOTE]  
> Pour permettre à un utilisateur d’utiliser le contrôle d’appel distant, vous devez fournir à l’utilisateur un URI de ligne et un URI de ligne serveur. Comme décrit dans <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tâches de déploiement pour le contrôle d’appel distant dans Lync Server 2013</A>, vous devez être sûr d’utiliser la syntaxe requise par la passerelle pour ces paramètres.<BR>Assurez-vous que le domaine dans l’URI ligne Server est le même que le domaine de destination que vous avez spécifié dans le paramètre MatchUri lorsque vous avez configuré l’itinéraire statique vers la passerelle.<BR>L’URI de ligne indique le numéro de téléphone attribué à l’utilisateur au format E. 164, avec le préfixe «TEL:» (par exemple, tel: + 14255550150). Si vous voulez configurer un numéro de poste, le format est tel: + 14255550150; ext = 111. Si vous avez précédemment configuré l’URI de ligne de l’utilisateur et que la valeur n’a pas changé, vous n’avez pas besoin de spécifier l’URI de ligne lorsque vous activez le contrôle d’appel distant de l’utilisateur.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Pour activer le contrôle d’appel distant pour les utilisateurs compatibles Lync à l’aide de Management Shell

1.  Connectez-vous à un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou en tant que rôle de contrôle d’accès basé sur le rôle auquel vous avez affecté l’applet de commande **Set-Csuser** .

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour utiliser l’applet de commande **Set-Csuser** pour configurer le contrôle d’appel distant pour un utilisateur existant Lync, procédez comme suit:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Par exemple :
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Pour configurer les utilisateurs pour le contrôle d’appel distant à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout (ou la première partie) du nom d’affichage, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez, puis cliquez sur ** Recherchez**.

5.  Dans la table, cliquez sur le compte d’utilisateur que vous voulez modifier.

6.  Dans le menu **édition** , cliquez sur **modifier**.

7.  Dans **téléphonie**, effectuez l’une des opérations suivantes:
    
      - Pour activer le contrôle d’appel distant et permettre à l’utilisateur de contrôler son téléphone PBX à partir de Lync 2013 pour passer des appels audio et des appels de PC à téléphone, cliquez sur **contrôle d’appel distant**. Dans **URI de ligne**, spécifiez le numéro de téléphone de l’utilisateur. Dans **URI Line Server**, spécifiez l’URI SIP de la passerelle SIP/CSTA.
    
      - Pour activer le contrôle d’appel distant, mais désactiver les appels audio de PC à PC et permettre uniquement à l’utilisateur de contrôler son téléphone PBX à partir de Lync 2013 pour passer des appels de PC à téléphone, cliquez sur **contrôle d’appel distant uniquement**. Dans **URI de ligne**, spécifiez le numéro de téléphone de l’utilisateur. Dans **URI Line Server**, spécifiez l’URI SIP de la passerelle SIP/CSTA.

8.  Lorsque vous avez terminé, cliquez sur **valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

