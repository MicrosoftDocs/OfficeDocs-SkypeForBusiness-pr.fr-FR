---
title: 'Lync Server 2013 : affichage des informations de profil de stratégie de bande passante réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb8583eb7d96443f755b0060aedf22c669ad3453
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Affichage des informations de profil de stratégie de bande passante réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis. Dans Microsoft Lync Server 2013, seules les modalités audio et vidéo peuvent se voir affecter des limites de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le panneau de configuration Lync Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Utilisez les procédures suivantes pour afficher un profil de stratégie de bande passante. Pour créer ou modifier un profil de stratégie de bande passante, reportez-vous à la rubrique [création ou modification de profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>Pour afficher un profil de stratégie de bande passante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Sur la page **stratégie de bande passante** , cliquez sur le profil de stratégie de bande passante que vous souhaitez afficher.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de profil de stratégie de bande passante réseau à l’aide des applets de commande Windows PowerShell

Les profils de bande passante réseau peuvent être affichés à l’aide de Windows PowerShell et de la cmdlet Get-CsNetworkBandwidthPolicyProfile. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>Pour afficher les informations de profil de stratégie de bande passante réseau

  - Pour afficher des informations sur tous les profils de stratégie de bande passante réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Suppression des profils de stratégie de bande passante réseau dans Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurer le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

