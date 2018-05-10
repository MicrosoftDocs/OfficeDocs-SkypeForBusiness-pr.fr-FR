---
title: Bloquer les appels entrants dans Skype pour les entreprises en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto: Skype for Business
localization_priority: Normal
ms.custom: Use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 9a9ff446d7b95588f1d9c2460db1284de717e557
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
 # <a name="block-inbound-calls"></a>Bloquer les appels entrants

Skype pour Business Online appelant Plans prend désormais en charge le blocage des appels entrants à partir du réseau téléphonique commuté (RTC). Cette fonctionnalité permet une liste globale du client de modèles de numéro à définir afin que l’ID d’appelant de chaque PSTN entrant appeler au client peut être vérifiée par rapport à la liste pour une correspondance. Si une correspondance est trouvée, un appel entrant est rejeté. 

Cette fonctionnalité de blocage d’appel entrant fonctionne uniquement sur les appels entrants provenant de la passerelle PSTN et fonctionne uniquement sur une base globale du client et n’est pas disponible par utilisateur.

Cette fonctionnalité n’est pas encore disponible pour le routage Direct.

>[Note] Les appelants bloqués peuvent se heurter comportements légèrement différents lorsqu’ils ont été bloqués. Le comportement dépendra comment opérateur l’appelant bloqués gère la notification de l’appel n’est pas autorisé à aboutir avec succès. Exemples peuvent inclure un message opérateur l’appel ne peut pas être effectué, ou simplement en supprimant l’appel.

## <a name="call-blocking-admin-controls-and-information"></a>Appel de blocage des informations et des contrôles d’administration
Contrôles d’administration pour les numéros de blocage sont fournies uniquement à l’aide de PowerShell. Modèles de bloc numéro sont définies comme des modèles d’expression régulière. L’ordre des expressions est sans importance – le premier modèle dans la liste entraînera l’appel est bloqué. Un nouveau numéro ou un modèle ajouté ou supprimé dans la liste bloquée liste des appelants peut prendre jusqu'à 24 heures pour le modèle actif.
## <a name="call-blocking-powershell-commands"></a>Appelez le blocage des commandes PowerShell

*InboundBlockedNumberPattern* Modèles de numéro sont gérés via les commandes *CsInboundBlockedNumberPattern* **New**, **obtenir**, **définir**et **Supprimer**.  

Vous pouvez gérer un modèle donné à l’aide de ces applets de commande, notamment la possibilité de faire basculer l’activation d’un modèle donné.
- *Get-CsInboundBlockedNumberPattern* Renvoie une liste de tous les modèles de numéro bloqués ajouté à la liste de clients, y compris le nom, Description, activé (True/False) et motif pour chacun.
- *Nouvelle CsInboundBlockedNumberPattern* Ajoute un modèle de numéro bloqué à la liste des clients.
- *Remove-CsInboundBlockedNumberPattern* Supprime un modèle de numéro bloqué dans la liste client.
- *Set-CsInboundBlockedNumberPattern* Modifie un ou plusieurs paramètres d’un modèle de numéro bloqué dans la liste des clients.
- *TenantBlockedCallingNumbers* L’affichage et l’activation de la fonctionnalité de blocage des appels entière est gérée via la CsTenantBlockingCallingNumbers commandes obtenir et définir. 
- *Get-CsTenantBlockedCallingNumbers* Renvoie les paramètres de la liste de numéros bloquée globale notamment activé (True/False). Il existe une stratégie de client globale unique qui ne peut être modifiée manuellement différente pour activer la fonctionnalité complètement activé/désactivé.
- *Set-CsTenantBlockedCallingNumbers* Permet de modifier les appels client globale bloqué pour être activé/désactivé au niveau du client.

### <a name="examples"></a>Exemples
#### <a name="blocking-a-number"></a>Blocage d’un nombre

Dans cet exemple,-activé et - paramètres Description sont facultatifs :

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 Création de qu'un nouveau modèle par défaut ajoute le modèle comme étant activé et la description est toujours et champ facultatif pour fournir plus d’informations. 

Nous vous conseillons de fournir un nom significatif pour mieux comprendre pourquoi le modèle a été ajouté. Dans le cas de simplement le blocage du courrier indésirable numéros, considéré comme nom de la règle de la même en tant que modèle de numéro de la mise en correspondance et ajouter des informations supplémentaires dans la description selon les besoins.

Modèles correspondent à l’aide d’Expressions régulières (regex). Laissez les temps de réplication avant de test et validation.

#### <a name="allowing-a-number"></a>Autorise un nombre

Dans cet exemple, le paramètre identity est requis :`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`
 
Si l’identité n’est pas connue, utilisez l’applet de commande *Get-CsInb undBlockedNumberPattern* pour le modèle approprié d’abord la localiser et notez l’identité. Ensuite, exécutez l’applet de commande *Supprimer* et transmettre la valeur d’identité appropriée.

Laissez les temps de réplication avant de test et validation.
#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de numéro
Exécution de cette applet de commande renverra les numéros d’une liste de toutes les entrées bloquée pour un client :`Get-CsInboundBlockedNumberPattern`

Utiliser PowerShell intégrée capacités de filtrage pour analyser les valeurs renvoyées selon les besoins.

#### <a name="a-note-on-regex"></a>Remarque sur l’expression régulière
Comme indiqué précédemment, le modèle de correspondance pour le blocage des appelants s’effectue à l’aide d’Expressions régulières (regex). Il existe plusieurs outils disponibles en ligne pour valider une correspondance d’expression régulière. Si vous n’êtes pas familiarisé avec les modèles d’expression régulière, il est recommandé que vous prenez le temps de vous familiariser avec les concepts de base et pour vous assurer que vous obtenez les résultats attendus, utilisez un outil pour la validation des correspondances de modèle avant d’ajouter de nouveaux bloqués correspond à votre client. 

## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion de l’entreprise en ligne à l’aide de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell )
