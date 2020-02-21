---
title: 'Lync Server 2013 : afficher la stratégie de code confidentiel des informations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5dad362c4291f83c6feb261247a0b90ba47e16
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>Afficher les stratégies de code confidentiel des informations dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez utiliser l’onglet **stratégie de code confidentiel** pour afficher l’authentification par code confidentiel des utilisateurs qui se connectent à Lync 2013 avec des téléphones IP. Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web. Pour plus d’informations, consultez la rubrique [modifier les paramètres de configuration d’un service Web existant dans Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Suivez ces étapes pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur.

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>Pour afficher des informations sur une stratégie de code confidentiel dans le panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Affichage des stratégies de code confidentiel à l’aide des applets de commande Windows PowerShell

Vous pouvez également afficher les stratégies de code confidentiel à l’aide de Windows PowerShell et de la cmdlet Get-applet cspinpolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-pin-policies"></a>Pour afficher les stratégies de code confidentiel

  - Pour afficher des informations sur toutes vos stratégies de code confidentiel, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsPinPolicy
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-applet cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier les paramètres de configuration d’un service Web existant dans Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Créer une stratégie de code confidentiel dans Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

