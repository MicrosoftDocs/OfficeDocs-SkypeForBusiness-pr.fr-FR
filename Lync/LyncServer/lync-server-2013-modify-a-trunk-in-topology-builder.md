---
title: "Mod. d’une jonction dans le générateur de topologie dans Lync Server 2013"
TOCtitle: "Mod. d’une jonction dans le générateur de topologie dans Lync Server 2013"
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49891416
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification d’une jonction dans le générateur de topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Suivez ces étapes pour modifier l’adresse IP média de remplacement et l’identificateur de contournement de remplacement d’une jonction.

## Pour modifier l’adresse IP média de remplacement d’une jonction

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsPstnGateway et modifiez le champ AlternateBypassId dans Lync Server Management Shell.
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

## Pour modifier le BypassID de remplacement d’une jonction

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsPstnGateway et modifiez le champ AlternateBypassId dans Lync Server Management Shell.
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

