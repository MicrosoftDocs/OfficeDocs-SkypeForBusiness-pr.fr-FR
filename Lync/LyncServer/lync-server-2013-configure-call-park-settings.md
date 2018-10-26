---
title: Configuration des paramètres de parcage d’appels dans Lync Server 2013
TOCTitle: Configuration des paramètres de parcage d’appels dans Lync Server 2013
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425886(v=OCS.15)
ms:contentKeyID: 49296947
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des paramètres de parcage d’appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Si vous ne voulez pas utiliser les paramètres de parcage d’appel par défaut, vous pouvez les personnaliser. Quand vous installez l’application de parcage d’appel, les paramètres globaux sont configurés par défaut. Vous pouvez modifier les paramètres globaux et définir également des paramètres spécifiques à un site. L’applet de commande **New-CsCpsConfiguration** permet de créer des paramètres spécifiques à un site. L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.

> [!NOTE]  
> Nous vous recommandons de configurer au moins l’option <strong>OnTimeoutURI</strong> pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.

Les applets de commande **New-CsCpsConfiguration** et **Set-CsCpsConfiguration** permettent de configurer les paramètres suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cette option :</th>
<th>Définit ceci :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>Laps de temps qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</p>
<p>La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale est de 10 minutes. La valeur par défaut est 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.</p>
<p>Les valeurs sont True ou False. La valeur par défaut est True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>Nombre de sonnerie de rappel d’un appel parqué avant qu’il ne soit transféré vers l’URI de remplacement spécifié pour le paramètre <strong>OnTimeoutURI</strong>. La valeur par défaut est 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>Adresse SIP de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur <strong>MaxCallPickupAttempts</strong> est atteinte.</p>
<p>La valeur doit être une URI SIP et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.</p></td>
</tr>
</tbody>
</table>


## Pour configurer les paramètres de parcage d’appel

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    > [!TIP]  
    > L’applet de commande <strong>Get-CsSite</strong> permet d’identifier le site. Pour plus d’informations, voir la documentation de Lync Server Management Shell.    
    Par exemple :
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

## Voir aussi

#### Tâches

[Personnalisation de l’attente musicale du parcage d’appels dans Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  

#### Autres ressources

[New-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite)

