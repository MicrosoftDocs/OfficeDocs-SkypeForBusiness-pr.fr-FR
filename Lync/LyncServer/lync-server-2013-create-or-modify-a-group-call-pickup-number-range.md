---
title: 'Lync Server 2013 : création ou modification d’une plage de numéros de prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd323e609a811a9735c966645c5176fb8784bb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Création ou modification d’une plage de numéros de prise d’appel de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Utilisez la procédure suivante pour créer ou modifier une plage de numéros de groupe de prise d’appel dans la table des orbites de parcage d’appel.

<div>


> [!NOTE]  
> Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel. Les plages de numéros de prise d’appel de groupe ne sont pas disponibles dans le panneau de configuration Lync Server.



</div>

<div>


> [!IMPORTANT]  
> La plage de numéros de groupe de prise d’appel doit être affectée d’un type de GroupPickup. Les utilisateurs sont activés pour la prise d’appel de groupe uniquement si le numéro de groupe auquel ils sont attribués est de type GroupPickup.



</div>

Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.

  - La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.

  - La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

  - Si la plage de numéros commence par le \* caractère \#ou, la plage doit être supérieure à 100.

  - Valeurs valides : doivent correspondre à la chaîne d'\[\\\*|\#\]expression\[ régulière ( ? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). Cela signifie que la valeur doit être une chaîne commençant par le caractère \* ou \# un nombre de 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou \#, le caractère suivant doit être un nombre de 1 à 9 (il ne peut pas être zéro). Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9, jusqu’à\#sept caractères supplémentaires (\*par exemple, «\*6000 », « 92000 », « 95551212 » et « 915551212 »). Si le premier caractère n’est \* pas \#ou, le premier caractère doit être un nombre compris entre 1 et 9 (il ne peut pas être zéro), suivi de huit caractères au maximum, chacun compris entre 0 et 9 (par exemple, « 915551212 », « 41212 », « 300 »).

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Pour créer ou modifier une plage de groupe de prise d’appel

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros de groupe de prise d’appel. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de prise d’appel.
    
    À partir de la ligne de commande, exécutez la commande suivante :
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Par exemple :
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    L’exemple suivant montre comment modifier une plage de numéros entre les orbites de parcage d’appel et les groupes de prise d’appel.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Utilisez cette applet de commande pour modifier le type affecté aux plages de numéros uniquement si vous avez initialement spécifié un type incorrect et que la plage de groupes n’est pas encore utilisée. Si vous modifiez la plage de numéros de CallPark à GroupPickup ou inversement et que la plage de numéros est déjà utilisée, le parcage d’appel ou la prise d’appel de groupe cessera de fonctionner pour cette plage de numéros. Par exemple, si vous modifiez une plage de numéros de CallPark à GroupPick, l’application de parcage d’appel ne peut plus utiliser cette plage d’orbites pour les appels de parcage.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

