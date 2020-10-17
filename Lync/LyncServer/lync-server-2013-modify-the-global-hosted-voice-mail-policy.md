---
title: 'Lync Server 2013 : modifier la stratégie de messagerie vocale hébergée globale'
description: 'Lync Server 2013 : modifier la stratégie de messagerie vocale hébergée globale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd5e16c78049ce79abd936a79b2025a14e45943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566860"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modifier la stratégie de messagerie vocale hébergée globale dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

La stratégie de messagerie vocale *globale* hébergée est installée avec Lync Server 2013. Vous pouvez la modifier en fonction de vos besoins, mais pas la renommer ni la supprimer. Pour modifier la stratégie globale, utilisez l’applet de commande Set-CsHostedVoicemailPolicy pour définir les paramètres sur les valeurs appropriées pour votre déploiement spécifique.

Pour plus d’informations sur la cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , voir la documentation de Lync Server Management Shell.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Pour modifier la stratégie de messagerie vocale hébergée globale

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsHostedVoicemailPolicy pour définir les paramètres de stratégie globale pour votre environnement. Par exemple, exécutez :
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Étant donné que cette commande ne spécifie pas le paramètre Identity de la stratégie, l’interface de ligne de commande Windows PowerShell définit les valeurs suivantes sur la stratégie de messagerie vocale globale hébergée :
    
      - **Destination** spécifie le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée alors que la stratégie affectée à l’utilisateur n’a pas de valeur Destination, l’activation échoue.
    
      - **Organisation** spécifie une liste séparée par des virgules des clients Exchange hébergeant des utilisateurs de Lync Server. Chaque locataire doit être spécifié avec son nom de domaine complet (FQDN) dans le service de messagerie unifiée Exchange hébergé.
    
    <div>
    

    > [!NOTE]  
    > Dans l’exemple de cmdlet précédent, la valeur « corp1.litwareinc.com » remplace toute valeur qui pourrait déjà figurer dans le paramètre Organization. Par exemple, si la stratégie contient déjà une liste d’organisations séparées par des virgules, la liste complète serait remplacée. Si vous souhaitez ajouter une organisation à la liste au lieu de remplacer toute la liste, exécutez une commande semblable à la suivante.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

