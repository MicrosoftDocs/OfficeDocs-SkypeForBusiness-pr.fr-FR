---
title: Gérer les entrées DNS lors de la désaffectation de votre environnement local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions sur la gestion des entrées DNS lors de la désaffectation de votre environnement Skype Entreprise local.
ms.openlocfilehash: 70255314ecf87d55ef578a4daa0390b46179349c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58735321"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Mettre à jour les entrées DNS pour permettre à votre organisation d’être Teams uniquement

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Les organisations qui avaient précédemment des déploiements locaux de Skype Entreprise Server ou Lync Server peuvent toujours avoir des entrées DNS qui pointent vers un déploiement local Skype Entreprise local. Ces enregistrements sont requis si votre organisation inclut des utilisateurs Skype Entreprise locaux. Toutefois, une fois que votre organisation n’a plus d’utilisateurs Skype Entreprise ou Lync Server locaux, ces enregistrements d’origine ne sont plus requis par le déploiement local et ces entrées DNS doivent être mises à jour pour pointer vers Microsoft 365 (ou dans certains cas **supprimés)** dans le cadre de votre migration de l’local vers Teams Uniquement. *Microsoft ne peut pas mettre à jour ces enregistrements DNS en votre nom.*

Lorsque vous tentez d’accorder TeamsOnly à l’ensemble du client, Teams vérifie le DNS pour déterminer si l’un de ces enregistrements DNS répertoriés ci-dessous existe dans chacun de vos domaines Microsoft 365 vérifiés dans votre organisation. Si des enregistrements sont trouvés et qu’ils pointent vers un autre point que Microsoft 365, la tentative de modification du mode de coexistence du client en TeamsOnly échouera par conception. Cela empêche les organisations hybrides avec des utilisateurs locaux d’appliquer par erreur le mode TeamsOnly au client, car cela rompreait la fédération pour tous les utilisateurs Skype Entreprise locaux de l’organisation (qu’ils utilisent Teams ou Skype Entreprise).


## <a name="how-to-identify-stale-dns-records"></a>Comment identifier les enregistrements DNS obsolètes

Pour identifier les enregistrements DNS qui empêchent votre organisation de devenir tous les enregistrements Teams Uniquement, vous pouvez utiliser le Centre d’administration Teams pour modifier le mode de coexistence en TeamsOnly. Go to **Org-wide setting**  ->  **Teams Upgrade**. Tous les enregistrements DNS qui empêchent l’organisation de devenir Teams Uniquement seront inclus dans le message d’erreur.  Si aucun enregistrement DNS n’est trouvé, le mode de coexistence de votre organisation est changé en TeamsOnly.   

Vous pouvez également utiliser Teams PowerShell pour faire la même chose, comme illustré ci-dessous :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Enregistrements DNS à mettre à jour

Si votre organisation n’a plus d’utilisateurs hébergés sur Skype Entreprise Server ou Lync Server, vous devez :

- Mettez à jour Skype Entreprise liste d’enregistrements DNS ci-dessous pour qu’elle pointe vers Microsoft 365 (au lieu du déploiement local). Si vous avez plusieurs domaines SIP, vous devez le faire pour chaque domaine SIP qui est un Microsoft 365 vérifié.

- Supprimez Skype Entreprise enregistrements DNS si le domaine SIP n’est plus utilisé. 

Dans chaque domaine où se trouvent les enregistrements suivants, mettez-les à jour comme suit :

| Type d’enregistrement | Nom | Durée de vie | Priorité | Pondération | Port | Value (Valeur) |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls._tcp |    3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip._tls | 3600     | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  N/A |   N/A |   N/A |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    N/A |   N/A  | N/A |    sipdir.online.lync.com |
|||||||

En outre, les enregistrements CNAME pour la meet ou dialin (le cas présent) peuvent être supprimés. Enfin, tous les enregistrements DNS Skype Entreprise votre réseau interne doivent être supprimés.

> [!Note] 
> Dans de rares cas, le fait de changer le DNS de pointage local en Microsoft 365 pour votre organisation peut entraîner l’arrêt de la fédération avec d’autres organisations jusqu’à ce que cette autre organisation met à jour sa configuration de fédération :
>
> - Toutes les organisations fédérées qui utilisent l’ancien modèle de fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour que leur organisation supprime le nom de domaine réservé au proxy. Ce modèle de fédération hérité n’est pas basé sur des enregistrements DNS SRV, de sorte qu’une telle configuration ne sera plus à jour une fois que votre organisation sera installée dans le cloud.
> 
> - Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed.online.lync. <span> com devra mettre à jour sa configuration pour l’activer. Cette situation n’est possible que si l’organisation fédérée est purement sur site et n’a jamais été fédérée avec un client hybride ou en ligne. Dans ce cas, la fédération avec ces organisations ne fonctionne pas tant qu’elles n’ont pas activé leur fournisseur d’hébergement.
>
> Si vous pensez que l’un de vos partenaires fédérés peut utiliser la fédération directe ou n’avoir été fédéré avec aucune organisation en ligne ou hybride, nous vous suggérons de leur envoyer une communication à ce sujet lorsque vous vous préparez à terminer votre migration vers le cloud.
  




