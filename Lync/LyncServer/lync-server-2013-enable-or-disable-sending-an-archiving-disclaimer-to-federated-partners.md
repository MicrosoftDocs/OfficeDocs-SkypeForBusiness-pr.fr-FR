---
title: Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f53e03ebfdc24ff969ff44a9b39149456ab3f16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Lors du déploiement de vos serveurs de périphérie et de la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez envoyer automatiquement l’exclusion de responsabilité aux partenaires fédérés. Si vous archivez des communications externes, vous devez autoriser l’envoi d’une exclusion de responsabilité d’archivage. Suivez la procédure décrite dans cette rubrique pour modifier cette configuration.

<div>


> [!NOTE]
> La procédure suivante suppose que vous avez déjà activé la Fédération pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Pour activer ou désactiver l’envoi d’une exclusion d’autorisation d’archivage aux partenaires fédérés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **configuration de Microsoft Edge Access**.

4.  Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modification de la configuration d’Access Edge**, sous **activer les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer un courrier électronique d’envoi aux partenaires fédérés** pour activer ou désactiver l’envoi automatique de l’exclusion de responsabilité de l’archivage.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement 2013 de Lync Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs fédérés. Pour plus d’informations, reportez-vous à [gérer les partenaires fédérés de XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) dans la documentation de déploiement ou la documentation des opérations. Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation relative aux opérations de déploiement ou aux opérations.

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’exclusion de responsabilité de l’archivage à l’aide d’applets de cmdlet Windows PowerShell

L’utilisation de la clause d’exclusion de responsabilité d’archivage peut être gérée à l’aide de Windows PowerShell et de l’applet de passe Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>Pour activer le démenti d’archivage

  - Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>Pour désactiver la clause d’exclusion de responsabilité d’archivage

  - Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

