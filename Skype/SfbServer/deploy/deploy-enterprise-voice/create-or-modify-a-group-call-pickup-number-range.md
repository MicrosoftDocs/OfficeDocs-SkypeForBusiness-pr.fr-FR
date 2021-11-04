---
title: Créer ou modifier une plage de numéro de prise d’appel de groupe dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Créez ou modifiez une plage de numéro de prise d’appel de groupe Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 661efa69d7c7a3264872c4d83b94372d8d9951f1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738920"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Créer ou modifier une plage de numéro de prise d’appel de groupe dans Skype Entreprise

Créez ou modifiez une plage de numéro de prise d’appel de groupe Skype Entreprise Server Voix Entreprise.

La prise d’appel de groupe est basée sur l’application de parcage d’appel. Lorsque vous déployez la prise d’appel de groupe, vous devez configurer la table des orbites de parcage d’appel avec des plages de numéros de téléphone désignés comme numéros de groupe de prise d’appel. Ces numéros de groupe sont les numéros que les utilisateurs composent pour prendre les appels qui sonnent pour un autre utilisateur.

Comme les numéros de numéros d’appels par parcage, les numéros de groupe de prise d’appel doivent être des extensions virtuelles qui ne sont pas affectées à un utilisateur ou à un téléphone. Chaque pool frontal sur lequel vous déployez la prise d’appel de groupe peut avoir une ou plusieurs plages de numéros de groupe de prise d’appel. Les plages de numéro de groupe doivent être globalement uniques dans votre déploiement et doivent être affectées en tant que type **GroupPickup.**

Utilisez la procédure suivante pour créer ou modifier une plage de numéro de groupe de prise d’appel dans la table des orbites de parcage d’appel.

> [!NOTE]
> Vous devez utiliser Skype Entreprise Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéro de prise d’appel de groupe dans la table des orbites de parcage d’appel. Les plages de numéro de prise d’appel de groupe ne sont pas disponibles dans Skype Entreprise Server panneau de commande.

Les plages de numéro de groupe de prise d’appel doivent respecter les règles suivantes :

- Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.

- La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.

- La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

- Si la plage de nombres commence par le caractère ou #, la plage doit être supérieure \* à 100.

- Valeurs valides : doit correspondre à la chaîne d’expression régulière ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Cela signifie que la valeur doit être une chaîne commençant par le caractère ou # ou un nombre de 1 à 9 (le premier caractère ne peut \* pas être un zéro). Si le premier caractère est ou #, le caractère suivant doit être un nombre \* de 1 à 9 (il ne peut pas être un zéro). Les caractères suivants peuvent être n’importe quel nombre de 0 à 9, jusqu’à sept caractères supplémentaires (par exemple, « #6000 », « \* 92000 », « 95551212 » et \* « 915551212 »). Si le premier caractère n’est pas ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être zéro), suivi de huit caractères au plus, chacun un nombre \* 0 à 9 (par exemple, « 915551212 », « 41212 », « 300 »).

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Pour créer ou modifier une plage de groupes de prise d’appel

1. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.

2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

3. Utilisez **New-CsCallParkOrbit** pour créer une nouvelle plage de numéros de groupe de prise d’appel. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de prise d’appel.

    À partir de la ligne de commande, exécutez la commande suivante :

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Par exemple :

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    L’exemple suivant montre comment modifier une plage de numéros des orbites de parcage d’appel aux groupes de prise d’appel.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Utilisez cette cmdlet pour modifier le type affecté aux plages de nombres uniquement si vous avez initialement spécifié le type incorrect et que la plage de groupes n’est pas encore en cours d’utilisation. Si vous modifiez la plage de numéro de CallPark en GroupPickup ou vice versa et que la plage de numéro est déjà en cours d’utilisation, le parcage d’appel ou la prise d’appel de groupe cesse de fonctionner pour cette plage de numéro. Par exemple, si vous modifiez une plage de numéro de CallPark en GroupPick, l’application de parcage d’appel ne peut plus utiliser cette plage d’orbites pour parer des appels.

## <a name="see-also"></a>Voir aussi

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Supprimer une plage d’orbites de parcage d’appel](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)