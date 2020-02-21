---
title: 'Lync Server 2013 : création ou modification d’une plage d’orbites de parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fe04aea0cc0d6ab38b0bfa9597b420d608c7597
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Utilisez l’une des procédures suivantes pour créer ou modifier une plage d’orbites de parcage d’appel.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Pour utiliser le panneau de configuration Lync Server pour créer ou modifier une plage de numéros pour les appels de parking

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Parcage d’appel**.

4.  Dans la page **Parcage d’appel**, effectuez l’une des opérations suivantes :
    
      - Pour créer une plage d’orbites, cliquez sur **Nouveau**. Dans **Nom**, tapez un nom permettant d’identifier cette plage de numéros.
        
        <div>
        

        > [!NOTE]  
        > Une fois que vous avez validé la plage d’orbites dans la base de données, vous ne pouvez plus modifier ce nom.

        
        </div>
    
      - Pour modifier une plage d’orbites existante, tapez une partie ou l’ensemble du nom de la plage d’orbites dans le champ de recherche. Dans la liste des orbites, cliquez sur l’orbite voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans le premier champ **Plage de numéros**, tapez le premier numéro de la plage de postes pour cette orbite de parcage d’appel et, dans le deuxième champ **Plage de numéros**, tapez le dernier numéro de la plage.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.</P>
    > <LI>
    > <P>La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.</P>
    > <LI>
    > <P>La plage d’orbites doit être unique. Cette plage ne peut pas chevaucher une autre plage.</P>
    > <LI>
    > <P>Si la plage d’orbites commence avec le caractère * ou #, la plage doit être supérieure à 100.</P>
    > <LI>
    > <P>Valeurs valides : doivent correspondre à la chaîne d’expression\*régulière ([| #] ? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Ainsi, chaque valeur doit être une chaîne commençant soit par le caractère * ou #, soit par un nombre de 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est * ou #, le caractère qui suit doit être un nombre de 1 à 9 (il ne peut être zéro). Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9, jusqu’à sept caractères supplémentaires (par exemple, « #6000 », «*92000 », «* 95551212 » et « 915551212 »). Si le premier caractère n’est pas * ou #, il doit être un nombre de 1 à 9 (pas de zéro) suivi de huit caractères maximum, chacun étant un nombre de 0 à 9 (par exemple : « 915551212 », « 41212 », « 300 »).</P>
    > <LI>
    > <P>Il ne doit pas y avoir plus de 50 000 orbites par pool. Chaque plage d’orbites comporte en général un maximum de 100 orbites. Mais les plages peuvent comporter jusqu’à 10 000 orbites. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, spécifiez « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.</P></LI></UL>

    
    </div>

6.  Dans nom **de domaine complet du serveur de destination**, cliquez sur le nom de domaine complet (FQDN) ou l’ID de service du service d’application qui héberge l’application de parcage d’appel. Tous les appels parqués sous forme de numéros dans la plage d’orbites spécifiée par le numéro de début et le numéro de fin seront routés vers ce serveur ou ce pool.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Pour utiliser Windows PowerShell afin de créer ou de modifier une plage de numéros pour les appels de parking

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros d’orbite. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros d’orbite.
    
    À partir de la ligne de commande, exécutez la commande suivante :
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Par exemple :
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    L’exemple suivant montre comment modifier les numéros d’une plage d’orbites existante,
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

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

