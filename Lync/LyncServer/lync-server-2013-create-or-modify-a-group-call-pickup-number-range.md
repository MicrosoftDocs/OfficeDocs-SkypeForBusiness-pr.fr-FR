---
title: Créer ou modifier une plage de numéros de prise d’appel de groupe
TOCTitle: Créer ou modifier une plage de numéros de prise d’appel de groupe
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945627(v=OCS.15)
ms:contentKeyID: 53095414
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier une plage de numéros de prise d’appel de groupe

 

_**Dernière rubrique modifiée :** 2013-01-30_

La procédure suivante vous permet de créer ou de modifier une plage de numéros de groupe de prise d’appel dans la table des numéros d’appel parqué.

> [!NOTE]  
> Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des numéros d’appel parqué. Les plages de numéros de prise d’appel de groupe ne sont pas disponibles dans le Panneau de configuration Lync Server.

> [!IMPORTANT]  
> Vous devez affecter le type GroupPickup à la plage de numéros de groupe de prise d’appel. Les utilisateurs ne sont activés pour la prise d’appel de groupe que si le numéro de groupe qui leur a été affecté est de type GroupPickup.

Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.

  - La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.

  - La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

  - Si la plage de numéros commence par le caractère \* ou \#, la plage doit être supérieure à 100.

  - Valeurs valides : ces valeurs doivent correspondre à la chaîne d’expression régulière (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}). Ainsi, chaque valeur doit être une chaîne commençant soit par le caractère \* ou \#, soit par un nombre de 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou \#, le caractère qui suit doit être un nombre de 1 à 9 (il ne peut être zéro). Les caractères suivants (jusqu’à sept caractères) peuvent être un nombre de 0 à 9, par exemple, « \#6000 », « \*92000 », « \*95551212 » et « 915551212 »). Si le premier caractère n’est pas \* ou \#, il doit être un nombre de 1 à 9 (pas de zéro) suivi de huit caractères maximum, chacun étant un nombre de 0 à 9 (par exemple : « 915551212 », « 41212 », « 300 »).

## Pour créer ou modifier une plage de numéros de groupe de prise d’appel

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros de groupe de prise d’appel. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de groupe de prise d’appel.
    
    Sur la ligne de commande, exécutez la commande suivante :
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Exemple :
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    L’exemple suivant montre comment convertir une plage de numéros d’appel parqué en une plage de numéros de groupes de prise d’appel.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    > [!IMPORTANT]  
    > N’utilisez cette applet de commande pour modifier le type affecté aux plages de numéros que si vous avez initialement spécifié un type incorrect et que la plage de groupe n’est pas encore utilisée. Si vous modifiez la plage de numéros en remplaçant CallPark par GroupPickup ou vice versa et que la plage de numéros est déjà utilisée, le parcage d’appel ou la prise d’appel de groupe cesse de fonctionner pour cette plage de numéros. Par exemple, si vous modifiez une plage de numéros en remplaçant CallPark par GroupPick, l’application de parcage d’appel ne peut plus utiliser cette plage de numéros pour parquer les appels.

## Voir aussi

#### Tâches

[Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### Autres ressources

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)

