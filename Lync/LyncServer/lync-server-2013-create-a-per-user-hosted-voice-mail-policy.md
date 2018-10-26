---
title: "Créer une strat. de mess. Voc. hébergée par utilisateur dans Lync Server 2013"
TOCtitle: "Créer une strat. de mess. Voc. hébergée par utilisateur dans Lync Server 2013"
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425867(v=OCS.15)
ms:contentKeyID: 49296906
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-24_

Une stratégie *par utilisateur* ne peut avoir d’incidence que sur des utilisateurs, groupes et objets Contact individuels. Pour déployer une stratégie par utilisateur, vous devez l’attribuer explicitement à un ou plusieurs utilisateurs, groupes ou objets Contact. Pour plus d’informations, voir [Attribuer une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Pour plus d’informations sur la gestion des stratégies de messagerie vocale hébergée par utilisateur, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## Pour créer une stratégie de messagerie vocale hébergée par utilisateur

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsHostedVoicemailPolicy pour créer la stratégie. Par exemple, exécutez :
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Dans l’exemple précédent, une stratégie de messagerie vocale hébergée est créée avec une étendue site et les paramètres suivants sont définis :
    
      - **Identity** spécifie un identificateur unique pour la stratégie qui englobe l’étendue. Pour une stratégie définie avec une étendue utilisateur, cette valeur de paramètre est définie en tant que chaîne simple, par exemple, ExRedmond.
    
      - **Destination** spécifie le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée alors que la stratégie affectée à l’utilisateur n’a pas de valeur Destination, l’activation échoue.
    
      - **Description** fournit des informations facultatives décrivant la stratégie.
    
      - **Organization** fournit la liste des locataires Exchange (séparés par des virgules) qui hébergent les utilisateurs Lync Server 2013. Chaque locataire doit être spécifié avec son nom de domaine complet (FQDN) dans le service de messagerie unifiée Exchange hébergé.

## Voir aussi

#### Tâches

[Attribuer une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

