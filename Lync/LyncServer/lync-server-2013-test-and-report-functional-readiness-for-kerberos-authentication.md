---
title: "Lync Server 2013 : Test et signalement de la disp. Fonct. de l’auth. Kerberos"
TOCTitle: Test et signalement de la disponibilité fonctionnelle de l’authentification Kerberos
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398925(v=OCS.15)
ms:contentKeyID: 49298965
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test et signalement de la disponibilité fonctionnelle de l’authentification Kerberos dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-01-16_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous pouvez faire appel à l’applet de commande Windows PowerShell**Test-CsKerberosAccountAssignment** pour tester et signaler la disponibilité fonctionnelle d’une attribution de site pour l’authentification Kerberos. Cette commande interroge le site spécifié dans le paramètre Identity obligatoire. Avec le paramètre Report facultatif, l’applet de commande enregistre un rapport HTML dans C:\\Logs sur l’ordinateur sur lequel la commande est exécutée. Le paramètre Verbose facultatif affiche des informations d’activité à l’écran.

## Pour tester et signaler la disponibilité fonctionnelle pour l’authentification Kerberos d’un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine qui exécute Lync Server 2013 ou sur l’ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez la commande suivante :
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Exemple :
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

