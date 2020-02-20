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
ms.openlocfilehash: 40beac1b249b09ef493b7f95cbb9380b307eda63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Après avoir fusionné la topologie et exécuté l’applet de commande **Import-applet cslegacyconfiguration** , vérifiez que vos stratégies et paramètres Office Communications Server 2007 R2 ont été importés dans Lync Server 2013. Le tableau suivant répertorie les stratégies et les paramètres que vous devez vérifier.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Stratégies et paramètres à vérifier après la migration


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si vous avez utilisé cette charge de travail :</th>
<th>Vérifiez ces stratégies et paramètres :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messagerie instantanée et conférence</p></td>
<td><p>Stratégie de présence</p>
<p>Stratégie de conférence</p></td>
</tr>
<tr class="even">
<td><p>Conférence rendez-vous</p></td>
<td><p>Numéros d’accès entrant</p>
<p>Plan de numérotation</p></td>
</tr>
<tr class="odd">
<td><p>Voix Entreprise</p></td>
<td><p>Stratégie de la voix</p>
<p>Itinéraires des communications vocales</p>
<p>Plan de numérotation</p>
<p>Paramètres d’utilisation PSTN</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>URL simples</p></td>
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

1.  Dans votre environnement Office Communications Server 2007 R2, notez les noms des plans de numérotation (anciennement appelés profils d’emplacement), les numéros d’accès entrant (numéros de téléphone et régions), les itinéraires des communications vocales et les stratégies répertoriées dans le tableau précédent, en plus des URL utilisées pour Communicator Web Access.

2.  Sur le serveur frontal Lync Server 2013, ouvrez le panneau de configuration Lync Server.

3.  Pour vérifier les stratégies de conférence importées, dans le volet de gauche, cliquez sur **Conférence**, sur **stratégie de conférence**, puis vérifiez que toutes les stratégies de conférence de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.
    
    <div>
    

    > [!NOTE]  
    > La stratégie de <STRONG>réunion</STRONG> des versions précédentes d’Office Communications Server est désormais appelée stratégie de conférence dans Lync Server 2013. De plus, le paramètre <STRONG>particpants anonyme</STRONG> des versions précédentes d’Office Communications Server est désormais un paramètre de la stratégie de conférence Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Dans Office Communications Server 2007 R2, si la stratégie de conférence n’est pas définie sur <STRONG>utiliser par utilisateur</STRONG>, seuls les paramètres de stratégie globale sont importés. Aucune autre stratégie de conférence n’est importée dans cette situation.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si les <STRONG>participants anonymes</STRONG> sont définis sur <STRONG>Enforce per User</STRONG> dans votre stratégie de conférence Office Communications Server 2007 R2, deux stratégies de conférence sont créées lors de la migration : une avec <STRONG>allowanonymousparticipantsinmeetings ayant</STRONG> définie sur <STRONG>true</STRONG> et une avec <STRONG>allowanonymousparticipantsinmeetings ayant</STRONG> défini sur <STRONG>false</STRONG>.

    
    </div>

4.  Pour vérifier les plans de numérotation importés, cliquez sur **Routage des communications vocales**, sur **Plan de numérotation**, puis contrôlez la présence de tous les plans de numérotation de votre environnement Office Communicator 2007 R2 dans la liste.
    
    <div>
    

    > [!NOTE]  
    > Dans Lync Server 2013, les <STRONG>profils d’emplacement</STRONG> sont désormais appelés <STRONG>plans de numérotation</STRONG>.

    
    </div>

5.  Pour vérifier les stratégies de voix importées, cliquez sur **Routage des communications vocales**, sur **Stratégie de voix**, puis contrôlez la présence de toutes les stratégies de voix de votre environnement Office Communicator 2007 R2 dans la liste.
    
    <div>
    

    > [!NOTE]  
    > Si la stratégie de voix n’est pas définie sur <STRONG>utiliser par utilisateur</STRONG> dans votre environnement Office Communications Server 2007 R2, seuls les paramètres de stratégie globale sont importés. Aucune autre stratégie de voix n’est importée dans ce cas.

    
    </div>

6.  Pour vérifier les itinéraires des communications vocales importés, cliquez sur **Routage des communications vocales**, sur **Itinéraire**, puis contrôlez la présence de tous les itinéraires des communications vocales de votre environnement Office Communicator 2007 R2 dans la liste.

7.  Pour vérifier les paramètres d’utilisation PSTN importés, cliquez sur **Routage des communications vocales**, sur **Utilisation PSTN**, puis contrôlez la présence de tous les paramètres d’utilisation PSTN de votre environnement Office Communicator 2007 R2 dans la liste.

8.  Pour vérifier les stratégies d’accès externe importées, cliquez sur **Fédération et accès externe**, sur **Stratégie d’accès externe**, puis contrôlez la présence de toutes les stratégies d’accès externe de votre environnement Office Communicator 2007 R2 dans la liste.

9.  Pour vérifier les stratégies d’archivage, cliquez sur **surveillance et archivage**, cliquez sur **stratégie d’archivage**, puis vérifiez que toutes les stratégies d’archivage de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.

10. Ouvrez Lync Server Management Shell.

11. Pour vérifier les stratégies de présence, sur la ligne de commande, tapez ce qui suit :
    
        Get-CsPresencePolicy
    
    En regardant le nom dans le paramètre **Identity** , vérifiez que toutes les stratégies de présence de votre environnement Office Communications Server 2007 R2 ont été importées.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Pour vérifier les stratégies et les paramètres à l’aide des applets de commande

1.  Ouvrez Lync Server Management Shell.

2.  Exécutez les applets de commande dans le tableau suivant pour vérifier les stratégies et les paramètres.
    
    La syntaxe de ces applets de commande ressemble à l’exemple suivant :
    
        Get-CsConferencingPolicy
    
    Pour plus d’informations sur ces applets de commande, exécutez :
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour cette stratégie ou ce paramètre :</th>
<th>Utilisez cette applet de commande :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stratégie de présence</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Stratégie de conférence</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>Numéros d’accès entrant</p></td>
<td><p><strong>Get-applet csdialinconferencingaccessnumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Plans de numérotation</p></td>
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
<td><p><strong>Get-applet csarchivingpolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

