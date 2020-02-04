---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Après avoir fusionné la topologie et exécuté l’applet de contrôle **Import-CsLegacyConfiguration** , assurez-vous que les stratégies et paramètres de votre serveur Office Communications Server 2007 R2 ont été importés dans Lync Server 2013. Le tableau suivant répertorie les stratégies et les paramètres que vous devez vérifier.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Stratégies et paramètres à vérifier après la migration


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si vous utilisez cette charge de travail :</th>
<th>Vérifiez les stratégies et les paramètres suivants :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messagerie instantanée et conférences</p></td>
<td><p>Politique de présence</p>
<p>Stratégie de conférence</p></td>
</tr>
<tr class="even">
<td><p>Conférence rendez-vous</p></td>
<td><p>Numéros d’accès rendez-vous</p>
<p>Plan de numérotation</p></td>
</tr>
<tr class="odd">
<td><p>Voix Entreprise</p></td>
<td><p>Stratégie de voix</p>
<p>Itinéraires des communications vocales</p>
<p>Plan de numérotation</p>
<p>Paramètres d’utilisation RTC</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>URL simples </p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs externes</p></td>
<td><p>Stratégies d’accès externe</p></td>
</tr>
<tr class="even">
<td><p>Archivage</p></td>
<td><p>Stratégie d’archivage</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Pour vérifier les stratégies et les paramètres

1.  Dans votre environnement Office Communications Server 2007 R2, notez les noms des plans de numérotation (auparavant appelés profils d’emplacement), les numéros d’accès entrants (numéros de téléphone d’accès au service de conférence), les itinéraires vocaux et les stratégies répertoriées dans le tableau précédent, en plus des URL utilisées pour Communicator Web Access.

2.  Sur le serveur frontal Lync Server 2013, ouvrez le panneau de configuration de Lync Server.

3.  Pour vérifier les stratégies de conférence importées, dans le volet gauche, cliquez sur **Conférence**, cliquez sur **stratégie de conférence**, puis vérifiez que toutes les stratégies de conférence dans votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.
    
    <div>
    

    > [!NOTE]  
    > La stratégie de <STRONG>réunion</STRONG> à partir de versions précédentes d’Office Communications Server est désormais désignée sous le nom de stratégie de conférence dans Lync Server 2013. Par ailleurs, le paramètre <STRONG>particpants anonyme</STRONG> à partir des versions précédentes d’Office Communications Server est désormais un paramètre dans la stratégie de conférence 2013 de Lync Server.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Dans Office Communications Server 2007 R2, si la stratégie de conférence n’est pas définie pour une <STRONG>utilisation par utilisateur</STRONG>, seuls les paramètres de stratégie globale sont importés. Aucune autre stratégie de conférence n’est importée dans cette situation.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si les <STRONG>participants anonymes</STRONG> sont définis pour <STRONG>appliquer par utilisateur</STRONG> dans votre stratégie de conférence Office Communications Server 2007 R2, deux stratégies de conférence sont créées lors de la migration : une avec <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> défini sur <STRONG>true</STRONG> et une avec <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> définie sur <STRONG>false</STRONG>.

    
    </div>

4.  Pour vérifier la présence de plans de numérotation, cliquez sur **routage des communications vocales**, sur **plan de numérotation**, puis vérifiez que tous les plans de numérotation dans votre environnement Office Communicator 2007 R2 sont inclus dans la liste.
    
    <div>
    

    > [!NOTE]  
    > Dans Lync Server 2013, les <STRONG>profils d’emplacement</STRONG> sont désormais désignés sous le nom de plan de <STRONG>numérotation</STRONG>.

    
    </div>

5.  Pour vérifier les stratégies vocales importées, cliquez sur **routage des communications**vocales, cliquez sur **politique vocale**, puis vérifiez que toutes les stratégies vocales dans votre environnement Office Communicator 2007 R2 sont incluses dans la liste.
    
    <div>
    

    > [!NOTE]  
    > Si la stratégie vocale n’est pas configurée pour être <STRONG>utilisée par utilisateur</STRONG> dans votre environnement Office Communications Server 2007 R2, seuls les paramètres de stratégie globale sont importés. Aucune autre politique vocale n’est importée dans cette situation.

    
    </div>

6.  Pour vérifier les itinéraires vocaux importés, cliquez sur **routage des communications**vocales, sur **routage, puis**Vérifiez que tous les itinéraires vocaux dans votre environnement Office Communicator 2007 R2 sont inclus dans la liste.

7.  Pour vérifier les paramètres d’utilisation RTC importés, cliquez sur **routage des communications vocales**, sur **utilisation PSTN**, puis vérifiez que les paramètres d’utilisation RTC de votre environnement Office Communicator 2007 R2 sont inclus dans la liste.

8.  Pour vérifier les stratégies d’accès externe importées, cliquez sur **Fédération et accès externe**, cliquez sur **stratégie d’accès externe**, puis vérifiez que toutes les stratégies d’accès externe dans votre environnement Office Communicator 2007 R2 sont incluses dans la liste.

9.  Pour vérifier les stratégies d’archivage, cliquez sur **surveillance et archivage**, sur **stratégie d’archivage**, puis vérifiez que toutes les stratégies d’archivage de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.

10. Ouvrez Lync Server Management Shell.

11. Pour vérifier les stratégies de présence, à partir de la ligne de commande, tapez ce qui suit :
    
        Get-CsPresencePolicy
    
    En examinant le nom dans le paramètre **Identity** , vérifiez que toutes les stratégies de présence de votre environnement Office Communications Server 2007 R2 ont été importées.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Pour vérifier les stratégies et les paramètres à l’aide d’applets de contrôle

1.  Ouvrez Lync Server Management Shell.

2.  Dans le tableau ci-dessous, exécutez les applets de commande pour vérifier les stratégies et les paramètres.
    
    La syntaxe de ces applets de commande est semblable à l’exemple suivant :
    
        Get-CsConferencingPolicy
    
    Pour plus d’informations sur ces cmdlets, exécutez :
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour cette stratégie ou ce paramètre :</th>
<th>Utilisez cette applet de cmdlet :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Politique de présence</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Stratégie de conférence</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>Numéros d’accès rendez-vous</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Plan de numérotation</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>Stratégie de voix</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Itinéraires des communications vocales</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>Utilisation PSTN</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>Stratégies d’accès externe</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Stratégie d’archivage</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

