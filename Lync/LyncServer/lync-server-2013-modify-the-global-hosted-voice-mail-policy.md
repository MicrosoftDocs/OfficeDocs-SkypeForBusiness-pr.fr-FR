---
title: "Mod. la stratégie de messagerie vocale hébergée globale dans Lync Server 2013"
TOCtitle: "Mod. la stratégie de messagerie vocale hébergée globale dans Lync Server 2013"
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412994(v=OCS.15)
ms:contentKeyID: 49299305
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifier la stratégie de messagerie vocale hébergée globale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-24_

La stratégie de messagerie vocale hébergée *globale* est installée avec Lync Server 2013. Vous pouvez la modifier en fonction de vos besoins, mais pas la renommer ni la supprimer. Pour modifier la stratégie globale, utilisez la cmdlet Set-CsHostedVoicemailPolicy pour définir les paramètres sur des valeurs adaptées à votre déploiement.

Pour plus d’informations sur la cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy), voir la documentation de Lync Server Management Shell.

## Pour modifier la stratégie de messagerie vocale hébergée globale

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet Set-CsHostedVoicemailPolicy pour définir les paramètres de stratégie globale pour votre environnement. Par exemple, exécutez :
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Cette commande ne spécifiant pas le paramètre Identity de la stratégie, l’interface de ligne de commande Windows PowerShell définit les valeurs suivantes sur la stratégie de messagerie vocale hébergée globale :
    
      - **Destination** spécifie le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée alors que la stratégie affectée à l’utilisateur n’a pas de valeur Destination, l’activation échoue.
    
      - **Organization** fournit la liste des clients Exchange (séparés par des virgules) qui hébergent les utilisateurs de Lync Server. Chaque client doit être spécifié avec son nom de domaine complet (FQDN) sur le service de messagerie unifiée Exchange hébergé.
    
    > [!NOTE]  
    > Dans la cmdlet de l’exemple précédent, la valeur corp1.litwareinc.com remplace toute valeur pouvant être déjà présente dans le paramètre Organisation. Par exemple, si la stratégie contient déjà une liste séparée par des virgules des organisations, toute la liste sera remplacée. Si vous souhaitez ajouter une organisation à la liste plutôt que de remplacer toute la liste, exécutez une commande similaire à celle-ci.

    ```
    $a = Get-CsHostedVoicemailPolicy
    $a.Organization += ",corp3.litwareinc.com"
    Set-CsHostedVoicemailPolicy -Organization $a.Organization
    ```

