---
title: "Aff. des inf. sur les jonctions SIP individuelles dans Lync Server 2013"
TOCtitle: "Aff. des inf. sur les jonctions SIP individuelles dans Lync Server 2013"
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49891489
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations sur les jonctions SIP individuelles dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Les jonctions SIP permettent de connecter le réseau téléphonique Voix sur IP (VoIP) de Microsoft Lync Server 2013 au réseau téléphonique commuté public. Dans la précédente version du produit, les jonctions servaient à acheminer les appels sortants d’un serveur de médiation vers une passerelle PSTN. Chaque passerelle était limitée à une seule jonction. Par conséquent, une passerelle PSTN et une jonction SIP étaient fondamentalement identiques. Pour les administrateurs, cela signifie qu’ils pouvaient consulter les informations relatives à une jonction SIP individuelle simplement en affichant les informations relatives à la passerelle PSTN associée.

Dans Lync Server 2013, toutefois, plusieurs jonctions peuvent désormais être affectées à une seule passerelle PSTN. Cela signifie que les passerelles et les jonctions ne sont plus fondamentalement identiques. En revanche, cela signifie aussi que les administrateurs doivent utiliser la nouvelle applet de commande [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) pour consulter les informations relatives à une jonction SIP individuelle.

L’applet de commande Get-CsTrunk peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des informations relatives à toutes vos jonctions SIP

  - La commande suivante retourne les informations relatives à toutes les jonctions SIP utilisées dans votre organisation :
    
        Get-CsTrunk

## Affichage des informations relatives à une jonction SIP spécifique

  - La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

## Affichage des informations relatives à toutes les jonctions SIP affectées à un pool

  - Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

