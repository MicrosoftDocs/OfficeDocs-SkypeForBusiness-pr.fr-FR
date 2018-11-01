---
title: Test des paramètres de configuration des jonctions SIP dans Lync Server 2013
TOCTitle: Test des paramètres de configuration des jonctions SIP dans Lync Server 2013
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49891534
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test des paramètres de configuration des jonctions SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les paramètres de configuration de jonction SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle PSTN (réseau téléphonique commuté), un système IP-PBX ou un contrôleur de session en périphérie (SBC) du côté fournisseur de services. Ces paramètres spécifient notamment :

  - l’activation de la fonctionnalité de contournement de média sur les jonctions ;

  - les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol) ;

  - la nécessité du chiffrement SRTP (Secure Real-time Transport Protocol) sur chaque jonction.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de commande Test-CsTrunkConfiguration pour vérifier qu’une jonction peut convertir un numéro composé par un utilisateur en numéro pouvant être traité par la passerelle.

Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration). Cette dernière peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Test des paramètres de configuration de jonction

  - Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir de façon correcte le numéro composé 4255551212.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

