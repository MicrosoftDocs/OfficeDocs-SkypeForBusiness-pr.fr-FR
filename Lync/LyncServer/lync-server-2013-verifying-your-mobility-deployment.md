---
title: 'Lync Server 2013 : Vérification du déploiement de mobilité'
TOCTitle: Vérification du déploiement de mobilité
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690024(v=OCS.15)
ms:contentKeyID: 49297718
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification du déploiement de mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Après avoir déployé le service de mobilité de Lync Server et le service de découverte automatique de Lync Server, exécutez une transaction test afin de vérifier que votre déploiement fonctionne correctement. Vous pouvez exécuter **Test-CsUcwaConference** pour tester la capacité de deux utilisateurs de clients Lync 2013 Mobile à créer, prendre part et communiquer lors d’une conférence. Pour utiliser cette transaction test, il vous faut deux utilisateurs test ou réels ainsi que leurs informations d’identification complètes.

Vous utilisez **Test-CsMcxP2PIM** pour tester l’envoi d’un message instantané entre deux utilisateurs de Lync 2010 Mobile. Comme avec **Test-CsUcwaConference**, vous utilisez deux utilisateurs réels ou deux utilisateurs tests prédéfinis.

## Pour tester la fonctionnalité de conférence pour les clients Lync 2013 Mobile

1.  Ouvrez une session en tant que membre du rôle CsAdministrator sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans la ligne de commande, tapez :
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    Vous pouvez définir des informations d’identification dans un script et les passer à l’applet de commande de test. Par exemple :
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

## Pour tester la messagerie instantanée de personne à personne pour Lync 2010 Mobile

1.  Ouvrez une session en tant que membre du rôle CsAdministrator sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans la ligne de commande, tapez :
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    Vous pouvez définir des informations d’identification dans un script et les passer à l’applet de commande de test. Par exemple :
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

## Voir aussi

#### Autres ressources

[Test-CsMcxP2PIM](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference)

