---
title: Création ou modification d’une plage de numéros de prise d’appel de groupe dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Créer ou modifier une plage de numéros de groupe d’appel collecte dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e67c8094bf66590d006fbce75f49258bb3f4f2a9
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business-2015"></a>Création ou modification d’une plage de numéros de prise d’appel de groupe dans Skype Entreprise 2015
 
Créer ou modifier une plage de numéros de groupe d’appel collecte dans Skype pour Business Server Enterprise Voice.
  
Groupe d’appel collecte est basé sur l’application de parcage d’appel. Lorsque vous déployez la collecte d’appel de groupe, vous devez configurer la table d’orbite de parcage d’appel avec des plages de numéros de téléphone qui sont désignés comme numéros d’appel groupe pickup. Ces numéros de groupe sont les numéros que les utilisateurs composent pour prendre des appels qui sonnent pour un autre utilisateur.
  
Tout comme les numéros d’appels parqués, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté. Chaque pool frontal où vous déployez le groupe d’appel collecte peut avoir une ou plusieurs plages appel collecte des numéros de groupe. Les plages de numéro de groupe doivent être globalement uniques dans votre déploiement, et doivent être affectées comme étant de type **GroupPickup**.
  
La procédure suivante vous permet de créer ou de modifier une plage de numéros de groupe de prise d’appel dans la table des numéros d’appel parqué. 
  
> [!NOTE]
> Vous devez utiliser Skype pour Business Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros collecte d’appel de groupe dans la table d’orbite de parcage d’appel. Plages de numéros de collecte des appels de groupe ne sont pas disponibles dans Skype pour le panneau de configuration serveur Business. 
  
Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :
  
- Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.
    
- La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.
    
- La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.
    
- Si la plage de numéros commence par le caractère \* ou #, la plage doit être supérieure à 100.
    
- Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ? [1-9] \d{0,7}) | (\d [1-9]{0,8}). Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou #, le caractère qui suit doit être un nombre de 1 à 9 (il ne peut pas être zéro). Les caractères suivants peuvent être n’importe quel nombre entre 0 et 9, jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000"«\*95551212" et « 915551212 »). Si le premier caractère n’est pas \* ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un nombre de 0 à 9 (par exemple, « 915551212 », « 41212 », « 300 »).
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Pour créer ou modifier une plage de numéros de groupe de prise d’appel

1. Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Utilisez **New-CsCallParkOrbit** pour créer une nouvelle plage de numéros de groupe collecte d’appel. **Set-CsCallParkOrbit** permet de modifier une plage existante de collecte d’appeler des numéros.
    
    À partir de la ligne de commande, exécutez la commande suivante :
    
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
    > N’utilisez cet applet de commande pour modifier le type affecté aux plages de numéros que si vous avez initialement spécifié un type incorrect et que la plage de groupe n’est pas encore utilisée. Si vous modifiez la plage de numéros en remplaçant CallPark par GroupPickup ou inversement et que la plage de numéros est déjà utilisée, CallPark et GroupPickup cesseront tous les deux de fonctionner pour cette plage de numéros. Par exemple, si vous modifiez une plage de numéros de CallPark à GroupPick, l’application de parcage d’appel peut ne plus utiliser cette plage d’orbites recours. 
  
## <a name="see-also"></a>Voir aussi

#### 

[Nouvelle-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Supprimer une plage d’orbites de parcage d’appel](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

