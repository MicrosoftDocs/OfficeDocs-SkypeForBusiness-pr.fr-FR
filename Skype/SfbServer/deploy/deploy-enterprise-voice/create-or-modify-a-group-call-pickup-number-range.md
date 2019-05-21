---
title: Création ou modification d’une plage de numéros de téléphone dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Créez ou modifiez une plage de numéros de téléphone dans Skype entreprise Server Voice.
ms.openlocfilehash: e81762e83598a9089e25536c74754bf11aae704f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286231"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Création ou modification d’une plage de numéros de téléphone dans Skype entreprise

Créez ou modifiez une plage de numéros de téléphone dans Skype entreprise Server Voice.

Le prélèvement d’appels de groupe est basé sur l’application de parc d’appels. Lorsque vous déployez le prélèvement d’appels de groupe, vous devez configurer la table orbite du parc d’appels avec des plages de numéros de téléphone désignés comme numéros de groupe de cueillette d’appel. Ces numéros de groupe sont les numéros que les utilisateurs composent pour prendre des appels qui sonnent pour un autre utilisateur.

Tout comme les numéros d’appels parqués, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté. Chaque pool frontal sur lequel vous déployez la capture d’appels de groupe peut avoir une ou plusieurs gammes de numéros de groupe de cueillette d’appel. Les plages de numéro de groupe doivent être globalement uniques dans votre déploiement, et doivent être affectées comme étant de type **GroupPickup**.

La procédure suivante vous permet de créer ou de modifier une plage de numéros de groupe de prise d’appel dans la table des numéros d’appel parqué.

> [!NOTE]
> Vous devez utiliser Skype entreprise Server Management Shell pour créer, modifier, supprimer et afficher les plages de numéros des numéros de téléphone dans la table de stationnement du parc. Les plages de numéros de capture d’appels de groupe ne sont pas disponibles dans le panneau de configuration Skype entreprise Server.

Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :

- Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.

- La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.

- La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

- Si la plage numérique commence par le caractère \* ou #, la plage doit être supérieure à 100.

- Valeurs valides: doit correspondre à la chaîne d’expression\\normale ([* | #] ? [1-{0,7}9] \d) | ([1-9] \d{0,8}). Cela signifie que la valeur doit être une chaîne commençant par le caractère \* ou # ou par un nombre 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou #, le caractère suivant doit être un nombre 1 à 9 (il ne peut pas être zéro). Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9 (par exemple, "#6000"\*, "92000"\*, "95551212" et "915551212"). Si le premier caractère n’est \* pas ou #, le premier caractère doit être un nombre compris entre 1 et 9 (il ne peut pas être zéro), suivi de huit caractères au maximum (par exemple, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Pour créer ou modifier une plage de numéros de groupe de prise d’appel

1. Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.

2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

3. Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros de groupe de prise d’appel. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de groupe de prise d’appel.

    Dans la ligne de commande, exécutez la commande suivante :

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Exemple :

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    L’exemple suivant montre comment convertir une plage de numéros d’appel parqué en une plage de numéros de groupes de prise d’appel.

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > N’utilisez cet applet de commande pour modifier le type affecté aux plages de numéros que si vous avez initialement spécifié un type incorrect et que la plage de groupe n’est pas encore utilisée. Si vous modifiez la plage de numéros en remplaçant CallPark par GroupPickup ou inversement et que la plage de numéros est déjà utilisée, CallPark et GroupPickup cesseront tous les deux de fonctionner pour cette plage de numéros. Par exemple, si vous modifiez une plage de nombres de CallPark à GroupPick, l’application de parc d’appels ne peut plus utiliser cette gamme d’orbites pour les appels de parc.

## <a name="see-also"></a>Voir aussi

[Nouveau-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Supprimer une gamme de stationnement d’appel](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
