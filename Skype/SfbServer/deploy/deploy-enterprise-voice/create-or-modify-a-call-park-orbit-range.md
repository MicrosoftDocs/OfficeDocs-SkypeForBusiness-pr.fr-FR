---
title: Créer ou modifier une gamme de parc d’appels dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Créez ou modifiez une table de plages d’orbites de stationnement d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: a5df3b61baf66a09bf968daf5c088e1c2ebf5734
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767897"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Créer ou modifier une gamme de parc d’appels dans Skype entreprise

Créez ou modifiez une table de plages d’orbites de stationnement d’appels dans Skype entreprise Server Voice.

Le parc d’appels utilise des orbites pour les appels en stationnement. Pour que les utilisateurs puissent parcer et récupérer des appels, vous devez configurer la table d’orbite du parc d’appels. Vous devez spécifier les plages de numéros d’extension (orbites) que votre organisation va réserver pour les appels de parking et définir le routage de ces plages en spécifiant le pool de parc d’appels qui gère chaque plage. Lorsque vous définissez des plages d’orbites, l’objectif est de disposer de suffisamment d’orbites pour ne pas avoir à réutiliser trop rapidement une orbite, mais sans que leur nombre soit trop élevé afin de pouvoir limiter le nombre de postes disponibles pour les utilisateurs ou d’autres services. Vous pouvez créer plusieurs plages d’orbites de parc d’appels pour chaque pool de serveurs Skype entreprise sur lequel l’application de parc d’appels est déployée. Chaque gamme de parking d’appel doit avoir un nom globalement unique et un ensemble unique d’extensions.

> [!IMPORTANT]
> Une plage d’orbites comprend généralement au moins 100 orbites. Chaque plage peut être plus importante à condition qu’elle contienne moins de 10 000 orbites et que chaque pool comporte moins de 50 000 orbites. Si une plage est trop petite, les orbites sont réutilisées plus rapidement.

Utilisez des blocs de postes virtuels (postes attribués à aucun utilisateur ni téléphone) pour vos plages d’orbites.

> [!NOTE]
> L’attribution de numéros de numérotation directe à l’intérieur de la table du parking d’appel n’est pas prise en charge.

Pour créer ou modifier une plage d’orbites de parcage d’appel, utilisez l’une des procédures ci-dessous.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Pour utiliser le panneau de configuration Skype entreprise Server pour créer ou modifier une plage de numéros pour les appels en stationnement

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **autorisations de configuration de délégué**.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Parcage d’appel**.

4. Dans la page **Parcage d’appel**, effectuez l’une des opérations suivantes :

   - Pour créer une plage d’orbites, cliquez sur **Nouveau**. Dans **Nom**, tapez un nom permettant d’identifier cette plage de numéros.

     > [!NOTE]
     > Une fois que vous avez validé la plage d’orbites dans la base de données, vous ne pouvez plus modifier ce nom.

   - Pour modifier une plage d’orbites existante, tapez une partie ou l’ensemble du nom de la plage d’orbites dans le champ de recherche. Dans la liste des orbites, cliquez sur l’orbite voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5. Dans le premier champ **Plage de numéros**, tapez le premier numéro de la plage de postes pour cette orbite de parcage d’appel et, dans le deuxième champ **Plage de numéros**, tapez le dernier numéro de la plage. Tenez compte des éléments suivants :

   - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.

   - La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.

   - La plage d’orbites doit être unique. Cette plage ne peut pas chevaucher une autre plage.

   - Si la plage orbite commence par le \* caractère ou #, la plage doit être supérieure à 100.

   - Valeurs valides : doit correspondre à la chaîne\\d’expression régulière 1-9] \d{0,7}) | ([1-9] \d{0,8}). Cela signifie que la valeur doit être une chaîne commençant par le caractère \* ou # ou par un nombre 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou #, le caractère suivant doit être un nombre 1 à 9 (il ne peut pas être zéro). Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9 (par exemple, "#6000"\*, "92000"\*, "95551212" et "915551212"). Si le premier caractère n’est \* pas ou #, le premier caractère doit être un nombre compris entre 1 et 9 (il ne peut pas être zéro), suivi de huit caractères au maximum (par exemple, "915551212", "41212", "300").

   - Il ne doit pas y avoir plus de 50 000 orbites par pool. Chaque plage d’orbites comporte en général un maximum de 100 orbites. Mais les plages peuvent comporter jusqu’à 10 000 orbites. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, spécifiez « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.

6. Dans **FQDN du serveur de destination**, cliquez sur le nom de domaine complet (FQDN) ou l’ID de service du service d’application qui héberge l’application de parc d’appels. Tous les appels parqués sous forme de numéros dans la plage d’orbites spécifiée par le numéro de début et le numéro de fin seront routés vers ce serveur ou ce pool.

7. Cliquez sur **Valider**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Pour utiliser Skype entreprise Server Management Shell pour créer ou modifier une plage de numéros pour les appels en stationnement

1. Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.

2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

3. Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros d’orbite. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros d’orbite.

    Dans la ligne de commande, exécutez la commande suivante :

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Exemple :

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    L’exemple ci-dessous montre comment modifier les numéros d’une plage d’orbites existante,

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Voir aussi

[Nouveau-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Supprimer une gamme de stationnement d’appel](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
