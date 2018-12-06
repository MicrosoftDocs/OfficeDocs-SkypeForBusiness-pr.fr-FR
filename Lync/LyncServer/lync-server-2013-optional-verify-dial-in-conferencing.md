---
title: 'Lync Server 2013 : (Facultatif) Vérification de la conférence rendez-vous'
TOCTitle: (Facultatif) Vérification de la conférence rendez-vous
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425905(v=OCS.15)
ms:contentKeyID: 49296980
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Facultatif) Vérification de la conférence rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2011-01-21_

Pour vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement, vous devez :

  - tester la page web Paramètres de conférence rendez-vous en vous connectant à l’URL simple ;

  - tester les numéros d’accès d’un pool spécifique en exécutant le script présenté dans la suite de cette rubrique. Ce script simule les appels vers les numéros d’accès. Pour l’utiliser, vous devez disposer de l’adresse SIP et des informations d’identification de l’un des clients de communications unifiées hébergés sur le pool.

Cette étape est facultative.

## Pour tester les numéros d’accès à un pool spécifique

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator** .

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante dans l’invite de commandes :
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    Le rapport obtenu indique Opération réussie ou Échec ainsi que des informations de diagnostic. L’indicateur -Verbose permet d’obtenir des informations plus détaillées ainsi que le nombre de numéros d’accès trouvés.

