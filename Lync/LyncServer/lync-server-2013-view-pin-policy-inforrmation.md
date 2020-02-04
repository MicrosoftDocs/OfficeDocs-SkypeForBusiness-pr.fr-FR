---
title: 'Lync Server 2013 : afficher les stratégies de code inforrmation'
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
ms.openlocfilehash: d5f63b2abcc1278211b70fd575bbead8ae875332
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>Afficher les inforrmation de stratégie de code confidentiel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez utiliser l’onglet **stratégie de code confidentiel** pour afficher l’authentification par code confidentiel (pin) des utilisateurs qui se connectent à Lync 2013 avec des téléphones IP. Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web. Pour plus d’informations, reportez-vous à [modifier les paramètres de configuration d’un service Web existant dans Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Suivez cette procédure pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur.

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>Pour afficher des informations sur une stratégie de code confidentiel dans le panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Affichage de stratégies de code confidentiel à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez également afficher les stratégies de code confidentiel à l’aide de Windows PowerShell et de l’applet de cmdlet Get-CsPinPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-view-pin-policies"></a>Pour afficher les stratégies de code confidentiel

  - Pour afficher des informations sur toutes les stratégies de code confidentiel, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsPinPolicy
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier les paramètres de configuration d’un service Web existant dans Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Créer une nouvelle stratégie de code confidentiel dans Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

