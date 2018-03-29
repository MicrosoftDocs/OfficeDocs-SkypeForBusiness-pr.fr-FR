---
title: Création ou modification d’une plage d’orbites de parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Créer ou modifier une table de plage appel Park orbite dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 3617fb739d56e395c31359c6cedae74e9fb63756
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a>Création ou modification d’une plage d’orbites de parcage d’appel dans Skype Entreprise 2015
 
Créer ou modifier une table de plage appel Park orbite dans Skype pour Business Server Voix Entreprise.
  
Parc d’appel utilise des orbites pour le stationnement des appels. Avant que les utilisateurs peuvent s’et récupérer des appels, vous devez configurer la table d’orbite de parc d’appel. Vous devez spécifier les plages de numéros d’extension (orbites) que votre organisation sera réserver pour le stationnement des appels et définissez la gamme pour les plages en spécifiant quel pool d’appel Park gère chaque plage. Lorsque vous définissez des plages d’orbites, l’objectif est de disposer de suffisamment d’orbites pour ne pas avoir à réutiliser trop rapidement une orbite, mais sans que leur nombre soit trop élevé afin de pouvoir limiter le nombre de postes disponibles pour les utilisateurs ou d’autres services. Vous pouvez créer plusieurs plages d’orbite de parc d’appel pour chaque Skype pour le pool de serveur de l’entreprise où l’application d’appel Park est déployée. Chaque plage d’orbite de parc d’appel doit avoir un nom unique et un ensemble unique d’extensions.
  
> [!IMPORTANT]
> Une plage d’orbites comprend généralement au moins 100 orbites. Chaque plage peut être plus importante à condition qu’elle contienne moins de 10 000 orbites et que chaque pool comporte moins de 50 000 orbites. Si une plage est trop petite, les orbites sont réutilisées plus rapidement. 
  
Utilisez des blocs de postes virtuels (postes attribués à aucun utilisateur ni téléphone) pour vos plages d’orbites. 
  
> [!NOTE]
> Affectation des numéros de numérotation directe vers l’intérieur (DID) sous forme de numéros d’orbite dans le parc d’appel orbite table n’est pas prise en charge. 
  
Pour créer ou modifier une plage d’orbites de parcage d’appel, utilisez l’une des procédures ci-dessous. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Utiliser Skype pour le panneau de configuration de Business Server permet de créer ou de modifier une plage de nombres pour le stationnement des appels

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **Déléguer les autorisations de configuration**.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Parcage d’appel**.
    
4. Dans la page **Parcage d’appel**, effectuez l’une des opérations suivantes :
    
  - Pour créer une plage d’orbites, cliquez sur **Nouveau**. Dans **Nom**, tapez un nom permettant d’identifier cette plage de numéros.
    
    > [!NOTE]
    > Une fois que vous avez validé la plage d’orbites dans la base de données, vous ne pouvez plus modifier ce nom. 
  
  - Pour modifier une plage d’orbites existante, tapez une partie ou l’ensemble du nom de la plage d’orbites dans le champ de recherche. Dans la liste des orbites, cliquez sur l’orbite voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans le premier champ **Plage de numéros**, tapez le premier numéro de la plage de postes pour cette orbite de parcage d’appel et, dans le deuxième champ **Plage de numéros**, tapez le dernier numéro de la plage. Gardez à l’esprit :
    
   - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.
    
   - La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.
    
   - La plage d’orbites doit être unique. Cette plage ne peut pas chevaucher une autre plage.
    
   - Si la plage d’orbite commence par le caractère \* ou #, la plage doit être supérieure à 100.
    
   - Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d 0,8 {}). Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être un zéro). Si le premier caractère est \* ou #, le caractère suivant doit être un nombre de 1 à 9 (il ne peut pas être un zéro). Les autres caractères peuvent être n’importe quel nombre de 0 à 9 jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000","\*95551212" et « 915551212 »). Si le premier caractère n’est pas \* ou #, le premier caractère doit être un numéro de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un nombre de 0 à 9 (par exemple, « 915551212 », « 41212 », « 300 »).
    
   - Il ne doit pas y avoir plus de 50 000 orbites par pool. Chaque plage d’orbites comporte en général un maximum de 100 orbites. Mais les plages peuvent comporter jusqu’à 10 000 orbites. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, spécifiez « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.
    
6. Dans **nom de domaine complet du serveur de destination**, cliquez sur le nom de domaine pleinement qualifié (FQDN) ou l’ID du service d’Application qui héberge l’application Park d’appel de service. Tous les appels parqués sous forme de numéros dans la plage d’orbites spécifiée par le numéro de début et le numéro de fin seront routés vers ce serveur ou ce pool.
    
7. Cliquez sur **Valider**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Utiliser Skype pour Business Server Management Shell pour créer ou modifier une plage de nombres pour le stationnement des appels

1. Ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires, comme décrit dans **Déléguer les autorisations de configuration**.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. **Nouveau-CsCallParkOrbit** permet de créer une plage de numéros d’orbite. Pour modifier une tranche de numéros d’orbite, utilisez **Set-CsCallParkOrbit** .
    
    À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Exemple :
     
   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    L’exemple ci-dessous montre comment modifier les numéros d’une plage d’orbites existante,
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Voir aussi

#### 

[Nouvelle-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Ensemble-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Supprimer une plage d’orbite de parc d’appel](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

