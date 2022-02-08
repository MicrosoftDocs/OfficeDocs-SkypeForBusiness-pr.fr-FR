---
title: Créer ou modifier une plage d’orbites de parcur d’appel dans Skype Entreprise
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Créez ou modifiez une table de plages d’orbites de parc Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 8e6061f77d59eef8029b5afc52ede0d5acc500c8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387352"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Créer ou modifier une plage d’orbites de parcur d’appel dans Skype Entreprise

Créez ou modifiez une table de plages d’orbites de parc Skype Entreprise Server Voix Entreprise.

Le parc d’appel utilise des orbites pour le parcier d’appels. Avant que les utilisateurs ne parent et récupèrent des appels, vous devez configurer la table des orbites de parcer des appels. Vous devez spécifier les plages de numéros de poste (orbites) que votre organisation réserve pour le parcage d’appels et définir le routage de ces plages en spécifiant le pool de parcage d’appel qui gère chaque plage. Lorsque vous définissez des plages d’orbites, l’objectif est de disposer de suffisamment d’orbites pour éviter d’avoir à réutiliser trop rapidement une orbite, mais sans que leur nombre soit trop élevé afin de pouvoir limiter le nombre de postes disponibles pour les utilisateurs ou d’autres services. Vous pouvez créer plusieurs plages d’orbites de parcage d’appel pour chaque pool Skype Entreprise Server où l’application de parcage d’appel est déployée. Chaque plage d’orbites de parcur d’appel doit avoir un nom global unique et un ensemble unique d’extensions.

> [!IMPORTANT]
> Une plage d’orbites comprend généralement au moins 100 orbites. Chaque plage peut être plus importante à condition qu’elle contienne moins de 10 000 orbites et que chaque pool comporte moins de 50 000 orbites. Si une plage est trop petite, les orbites sont réutilisées plus rapidement.

Utilisez des blocs de postes virtuels (postes attribués à aucun utilisateur ni téléphone) pour vos plages d’orbites.

> [!NOTE]
> L’affectation de numéros DID (Direct Inward Dialing) en tant que numéros d’orbite dans la table des orbites de parcage d’appel n’est pas prise en charge.

Utilisez l’une des procédures suivantes pour créer ou modifier une plage d’orbites de parcage d’appel.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Pour utiliser Skype Entreprise Server de contrôle d’accès pour créer ou modifier une plage de numéros pour le parc d’appels

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Parcage d’appel**.

4. Dans la page **Parcage d’appel**, effectuez l’une des opérations suivantes :

   - Pour créer une plage d’orbites, cliquez sur **Nouveau**. Dans **Nom**, tapez un nom permettant d’identifier cette plage de numéros.

     > [!NOTE]
     > Une fois que vous avez validé la plage d’orbites dans la base de données, vous ne pouvez plus modifier ce nom.

   - Pour modifier une plage d’orbites existante, tapez une partie ou l’ensemble du nom de la plage d’orbites dans le champ de recherche. Dans la liste des orbites, cliquez sur l’orbite voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5. Dans le premier champ **Plage de numéros**, tapez le premier numéro de la plage de postes pour cette orbite de parcage d’appel et, dans le deuxième champ **Plage de numéros**, tapez le dernier numéro de la plage. N’ignorez pas :

   - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.

   - La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.

   - La plage d’orbites doit être unique. Cette plage ne peut pas chevaucher une autre plage.

   - Si la plage d’orbites commence par le caractère ou \* #, la plage doit être supérieure à 100.

   - Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\*|#]?[ 1-9]\d{0,7})| ([1-9]\d{0,8}). Cela signifie que la valeur doit \* être une chaîne commençant par le caractère ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être un zéro). Si le premier caractère est \* ou #, le caractère suivant doit être un nombre de 1 à 9 (il ne peut pas être un zéro). Les caractères suivants peuvent être n’importe quel nombre de 0 à 9, jusqu’à sept caractères supplémentaires (par exemple, « #6000\* », « 92000\* », « 95551212 » et « 915551212 »). \* Si le premier caractère n’est pas ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être zéro), suivi de huit caractères au plus, chacun un nombre 0 à 9 (par exemple, « 915551212 », « 41212 », « 300 »).

   - Il ne doit pas y avoir plus de 50 000 orbites par pool. Chaque plage d’orbites comporte en général un maximum de 100 orbites. Mais les plages peuvent comporter jusqu’à 10 000 orbites. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, spécifiez « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.

6. Dans **le nom de** domaine complet du serveur de destination, cliquez sur le nom de domaine complet (FQDN) ou l’ID de service du service d’application qui héberge l’application de parcage d’appel. Tous les appels parqués sous forme de numéros dans la plage d’orbites spécifiée par le numéro de début et le numéro de fin seront routés vers ce serveur ou ce pool.

7. Cliquez sur **Valider**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Pour utiliser Skype Entreprise Server Management Shell pour créer ou modifier une plage de numéros pour le parc d’appels

1. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.

2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

3. Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros d’orbite. Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros d’orbite.

    À partir de la ligne de commande, exécutez la commande suivante :

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Par exemple :

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    L’exemple suivant montre comment modifier les numéros d’une plage d’orbites existante,

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Voir aussi

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Supprimer une plage d’orbites de parcage d’appel](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)