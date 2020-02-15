---
title: 'Lync Server 2013 : créer des stratégies d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7b815f533661fb553c7b9217f23b70f0027c559
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a>Créer des stratégies d’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

Lync Server utilise une stratégie d’emplacement pour activer les clients Lync pour E9-1-1 lors de l’inscription du client. Une stratégie d’emplacement contient les paramètres qui définissent comment E9-1-1 sera implémenté.

Vous pouvez modifier la stratégie d’emplacement globale et créer des stratégies d’emplacement marquées. Un client obtient une stratégie globale lorsqu’il ne se trouve pas dans un sous-réseau avec une stratégie d’emplacement associée, ou lorsque le client n’a pas reçu directement une stratégie d’emplacement. Les stratégies marquées sont affectées à des sous-réseaux ou des utilisateurs.

Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administration CsVoiceAdministrator, ou dispose de droits et d’autorisations d’administrateur équivalents.

Pour obtenir une description complète des stratégies d’emplacement, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md). Dans cette procédure, les cmdlets utilisent une stratégie d’emplacement définie à l’aide des valeurs suivantes :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Élément</th>
<th>Valeur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>Clause d’exclusion</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>La stratégie de votre entreprise exige que vous définiez un emplacement. Si vous ne définissez pas d’emplacement, les services d’urgence ne seront pas en mesure de vous localiser en cas d’urgence. Définissez un emplacement.</p></td>
</tr>
<tr class="even">
<td><p>Uselocationfore911only était</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>Pstnusage ne figure</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>bilatéral</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>n°2</strong></p></td>
</tr>
</tbody>
</table>


Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>Pour créer des stratégies d’emplacement

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.
    
    <div>
    

    > [!NOTE]  
    > CsLocationPolicy échoue si le paramètre de <STRONG>pstnusage ne figure</STRONG> n’est pas déjà dans la liste globale des PstnUsages.

    
    </div>

2.  Si vous le souhaitez, exécutez l’applet de commande suivante pour modifier la stratégie d’emplacement globale :
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Exécutez la commande suivante pour créer une stratégie d’emplacement étiquetée.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Exécutez l’applet de commande suivante pour appliquer la stratégie d’emplacement marquée créée à l’étape 3 à une stratégie utilisateur.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

