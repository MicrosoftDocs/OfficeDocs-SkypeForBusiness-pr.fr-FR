---
title: Créer des stratégies d’emplacement dans Lync Server 2013
TOCTitle: Créer des stratégies d’emplacement dans Lync Server 2013
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413006(v=OCS.15)
ms:contentKeyID: 49299296
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer des stratégies d’emplacement dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lync Server utilise une stratégie d’emplacement pour que les clients Lync puissent utiliser le système E9-1-1 lors de leur inscription. Une stratégie d’emplacement contient les paramètres qui définissent les modalités d’implémentation du système E9-1-1.

Vous pouvez modifier la stratégie d’emplacement globale et créer de nouvelles stratégies d’emplacement avec balise. Un client obtient une stratégie globale lorsqu’il ne se situe pas dans un sous-réseau avec une stratégie d’emplacement associée, ou lorsque le client n’a pas été directement affecté à une stratégie d’emplacement. Les stratégies avec balise sont assignées aux sous-réseaux ou aux utilisateurs.

Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins ou d’un rôle administratif CsVoiceAdministrator ou encore qui possède des droits et autorisations d’administrateur équivalents.

Pour obtenir une description complète des stratégies d’emplacement, consultez [Définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md). Les cmdlets de cette procédure utilisent une stratégie d’emplacement définie à l’aide des valeurs suivantes :


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
<td><p><strong>Clause d’exclusion de responsabilité</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>La stratégie de votre société exige que vous définissiez un emplacement. Si vous ne le faites pas, les services d’urgence ne pourront pas vous localiser en cas d’urgence. Veuillez définir un emplacement.</p></td>
</tr>
<tr class="even">
<td><p>UseLocationForE911Only</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
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
<td><p><strong>twoway</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir la documentation Lync Server Management Shell pour les cmdlets suivantes :

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

## Pour créer des stratégies d’emplacement

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.
    
    > [!NOTE]  
    > CsLocationPolicy échouera si le paramètre pour <strong>PstnUsage</strong> ne figure pas déjà dans la liste Global de PstnUsages.

2.  Si vous le souhaitez, exécutez la cmdlet suivante pour modifier la stratégie d’emplacement globale :
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Exécutez l’opération suivante pour créer une stratégie d’emplacement avec balise.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Exécutez la cmdlet suivante pour appliquer la stratégie d’emplacement avec balise créée à l’étape 3 à une stratégie d’utilisateur.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

