---
title: 'Lync Server 2013: création ou modification d’une plage de numéros de capture d’appels de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Create or modify a Group Call Pickup number range in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-30_

La procédure suivante vous permet de créer ou de modifier une plage de numéros de groupe de prise d’appel dans la table des numéros d’appel parqué.

<div>


> [!NOTE]  
> Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de capture d’appels de groupe dans la table de stationnement du parc. Les plages de numéros des numéros de téléphone ne sont pas disponibles dans le panneau de configuration de Lync Server.



</div>

<div>


> [!IMPORTANT]  
> La plage de numéros de groupe de capture d’appel doit être affectée à un type de GroupPickup. Les utilisateurs sont activés pour la cueillette de groupe uniquement si le numéro de groupe auquel ils sont attribués est du type GroupPickup.



</div>

Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.

  - La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.

  - La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

  - Si la plage numérique commence par le caractère \* ou \#, la plage doit être supérieure à 100.

  - Valeurs valides: doit correspondre à la chaîne d'\[\\\*|\#\]expression\[ normale (? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). Cela signifie que la valeur doit être une chaîne commençant par le caractère \* ou \# par un nombre 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou \#, le caractère suivant doit être un nombre 1 à 9 (il ne peut pas être zéro). Les caractères suivants peuvent être compris entre 0 et 9 (par exemple, "\#6000", "\*92000", "\*95551212" et "915551212"). Si le premier caractère n’est \* pas \#ou, le premier caractère doit être un chiffre compris entre 1 et 9 (il ne peut pas être zéro), suivi de huit caractères au maximum (par exemple, "915551212", "41212", "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Pour créer ou modifier une plage de numéros de groupe de prise d’appel

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros de groupe de prise d’appel. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de groupe de prise d’appel.
    
    Dans la ligne de commande, exécutez la commande suivante :
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Exemple :
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    L’exemple suivant montre comment convertir une plage de numéros d’appel parqué en une plage de numéros de groupes de prise d’appel.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > N’utilisez cet applet de commande pour modifier le type affecté aux plages de numéros que si vous avez initialement spécifié un type incorrect et que la plage de groupe n’est pas encore utilisée. Si vous modifiez la plage de numéros en remplaçant CallPark par GroupPickup ou inversement et que la plage de numéros est déjà utilisée, CallPark et GroupPickup cesseront tous les deux de fonctionner pour cette plage de numéros. Par exemple, si vous modifiez une plage de nombres de CallPark à GroupPick, l’application de parc d’appels ne peut plus utiliser cette gamme d’orbites pour les appels de parc.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer une gamme de stationnement d’appels dans Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[Nouveau-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

