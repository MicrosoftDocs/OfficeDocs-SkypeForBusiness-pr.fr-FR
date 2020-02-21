---
title: Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés
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
ms.openlocfilehash: 7f0715a7fc0dd9ab81d84fd996d5b87682af3f69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la notification d’exclusion relative à l’archivage doit être automatiquement envoyée aux partenaires fédérés. Si vous archivez des communications externes, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage. Utilisez la procédure de cette rubrique pour modifier cette configuration.

<div>


> [!NOTE]
> La procédure suivante suppose que vous avez déjà activé la fédération pour votre entreprise. Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Pour activer ou désactiver l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, sous **Autoriser les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** pour activer ou désactiver l’envoi automatique d’une notification d’exclusion relative à l’archivage.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Lync Server 2013, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, consultez la rubrique [Manage XMPP Federated Partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) dans la documentation de déploiement ou la documentation des opérations. Pour plus d’informations sur le contrôle de l’accès à des domaines fédérés spécifiques, reportez-vous à la rubrique [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation sur le déploiement ou les opérations.

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la clause d’exclusion de responsabilité pour l’archivage à l’aide des applets de commande Windows PowerShell

L’utilisation de la clause d’exclusion de responsabilité d’archivage peut être gérée à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>Pour activer la clause d’exclusion de responsabilité pour l’archivage

  - Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>Pour désactiver la clause d’exclusion de responsabilité pour l’archivage

  - Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

