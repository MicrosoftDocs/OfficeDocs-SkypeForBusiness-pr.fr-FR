---
title: Vérification des paramètres de configuration
TOCTitle: Vérification des paramètres de configuration
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204848(v=OCS.15)
ms:contentKeyID: 49297018
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification des paramètres de configuration

 

_**Dernière rubrique modifiée :** 2015-03-09_

Une fois que vous avez fusionné la topologie et exécuté l’applet de commande **Import-CsLegacyConfiguration** , vérifiez que vos stratégies et paramètres Office Communications Server 2007 R2 ont été importés dans Lync Server 2013. Le tableau ci-dessous répertorie les stratégies et les paramètres que vous devez vérifier.

## Stratégies et paramètres à vérifier après la migration


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
<p>Plans de numérotation</p></td>
</tr>
<tr class="odd">
<td><p>Voix Entreprise</p></td>
<td><p>Stratégie de voix</p>
<p>Itinéraires des communications vocales</p>
<p>Plans de numérotation</p>
<p>Paramètres d’utilisation RTC</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
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


## Pour vérifier les stratégies et les paramètres

1.  Dans votre environnement Office Communications Server 2007 R2, notez les noms des plans de numérotation (anciennement appelés « profils d’emplacement »), les numéros d’accès entrant (régions et numéros téléphoniques d’accès de l’Intendant Conférence), les itinéraires des communications vocales et les stratégies répertoriées dans le tableau précédent, qui viennent s’ajouter aux URL utilisées pour Communicator Web Access.

2.  Sur le serveur frontal Lync Server 2013, ouvrez le Panneau de configuration Lync Server.

3.  Pour vérifier les stratégies de conférence importées, dans le volet gauche, cliquez sur **Conférence** , sur **Stratégie de conférence** , puis contrôlez la présence de toutes les stratégies de conférence de votre environnement Office Communications Server 2007 R2 dans la liste.
    
    > [!NOTE]  
    > La stratégie <strong>Réunion</strong> issue de versions précédentes d’Office Communications Server est désormais appelée stratégie de conférence dans Lync Server 2013. En outre, le paramètre <strong>Participants anonymes</strong> des versions précédentes d’Office Communications Server est à présent un paramètre de stratégie de conférence Lync Server 2013.    
    > [!NOTE]  
    > Dans Office Communications Server 2007 R2, si la stratégie de conférence n’a pas la valeur <strong>Utiliser par utilisateur</strong> , seuls les paramètres de stratégie globale sont importés. Aucune autre stratégie de conférence n’est importée dans ce cas.    
    > [!NOTE]  
    > Si <strong>Participants anonymes</strong> a la valeur <strong>Appliquer par utilisateur</strong> dans votre stratégie de conférence Office Communications Server 2007 R2, deux stratégies de conférence sont créées lors de la migration : l’une avec <strong>AllowAnonymousParticipantsInMeetings</strong> ayant la valeur <strong>True</strong> et l’autre avec <strong>AllowAnonymousParticipantsInMeetings</strong> ayant la valeur <strong>False</strong> .

4.  Pour vérifier les plans de numérotation importés, cliquez sur **Routage des communications vocales** , sur **Plan de numérotation** , puis contrôlez la présence de tous les plans de numérotation de votre environnement Office Communicator 2007 R2 dans la liste.
    
    > [!NOTE]  
    > Dans Lync Server 2013, les <strong>profils d’emplacement</strong> sont appelés <strong>plans de numérotation</strong> .

5.  Pour vérifier les stratégies de voix importées, cliquez sur **Routage des communications vocales** , sur **Stratégie de voix** , puis contrôlez la présence de toutes les stratégies de voix de votre environnement Office Communicator 2007 R2 dans la liste.
    
    > [!NOTE]  
    > Dans votre environnement Office Communications Server 2007 R2, si la stratégie de voix n’a pas la valeur <strong>Utiliser par utilisateur</strong> , seuls les paramètres de stratégie globale sont importés. Aucune autre stratégie de voix n’est importée dans ce cas.

6.  Pour vérifier les itinéraires des communications vocales importés, cliquez sur **Routage des communications vocales** , sur **Itinéraire** , puis contrôlez la présence de tous les itinéraires des communications vocales de votre environnement Office Communicator 2007 R2 dans la liste.

7.  Pour vérifier les paramètres d’utilisation RTC importés, cliquez sur **Routage des communications vocales** , sur **Utilisation RTC** , puis contrôlez la présence de tous les paramètres d’utilisation RTC de votre environnement Office Communicator 2007 R2 dans la liste.

8.  Pour vérifier les stratégies d’accès externe importées, cliquez sur **Fédération et accès externe** , sur **Stratégie d’accès externe** , puis contrôlez la présence de toutes les stratégies d’accès externe de votre environnement Office Communicator 2007 R2 dans la liste.

9.  Pour vérifier les stratégies d’archivage, cliquez sur **Surveillance et archivage** , sur **Stratégie d’archivage** , puis contrôlez la présence de toutes les stratégies d’archivage de votre environnement Office Communications Server 2007 R2 dans la liste.

10. Ouvrez Lync Server Management Shell.

11. Pour vérifier les stratégies de présence, dans la ligne de commande, tapez ce qui suit :
    
        Get-CsPresencePolicy
    
    En regardant le nom qui figure dans le paramètre **Identité** , vérifiez que toutes les stratégies de présence de votre environnement Office Communications Server 2007 R2 ont été importées.

## Pour vérifier les stratégies et les paramètres à l’aide des applets de commande

1.  Ouvrez Lync Server Management Shell.

2.  Exécutez les applets de commande du tableau suivant pour vérifier les stratégies et les paramètres.
    
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
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
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
<td><p>Utilisation RTC</p></td>
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

