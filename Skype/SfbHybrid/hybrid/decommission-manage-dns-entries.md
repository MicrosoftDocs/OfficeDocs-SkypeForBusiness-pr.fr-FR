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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions sur la gestion des entrées DNS lors de la désaffectation de votre environnement Skype Entreprise local.
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458985"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Mettre à jour les entrées DNS pour permettre à votre organisation d’être Teams uniquement

Les organisations qui avaient précédemment des déploiements locaux de Skype Entreprise Server ou Lync Server peuvent toujours avoir des entrées DNS qui pointent vers un déploiement local Skype Entreprise local. Ces enregistrements sont requis si votre organisation inclut des utilisateurs Skype Entreprise locaux. Toutefois, une fois que votre organisation n’a plus d’utilisateurs locaux Skype Entreprise ou Lync Server, ces enregistrements ne sont plus requis. En fait, dans le cadre de la migration de l’local vers Teams, ces enregistrements doivent être mis à jour pour pointer vers Microsoft 365 ou supprimés. Microsoft ne peut pas prendre cette étape pour vous.

Lorsque vous tentez d’accorder TeamsOnly à l’ensemble du client, Teams vérifie DNS pour déterminer si l’un de ces enregistrements DNS existe pour votre organisation. Si des enregistrements sont trouvés et qu’ils pointent vers un autre point que Microsoft 365, la tentative de modification du mode de coexistence du client en TeamsOnly échouera par conception. Cette conception permet d’empêcher les organisations hybrides avec des utilisateurs locaux d’appliquer par erreur le mode TeamsOnly au client, car cela a pour conséquence de rompre la fédération pour tous les utilisateurs Skype Entreprise locaux (qu’ils utilisent Teams ou Skype Entreprise).

En outre, ces enregistrements doivent être mis à jour afin que vous pouvez accorder TeamsOnly à l’ensemble du client.

> [!Note] 
> Dans de rares cas, le fait de changer le DNS de pointage local en Microsoft 365 pour votre organisation peut entraîner l’arrêt de la fédération avec d’autres organisations jusqu’à ce que cette autre organisation met à jour sa configuration de fédération :
>
> - Toutes les organisations fédérées qui utilisent l’ancien modèle de fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour que leur organisation supprime le nom de domaine réservé au proxy. Ce modèle de fédération hérité n’est pas basé sur des enregistrements DNS SRV, de sorte qu’une telle configuration ne sera plus à jour une fois que votre organisation sera installée dans le cloud.
> 
> - Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed.online.lync. <span> com devra mettre à jour sa configuration pour l’activer. Cette situation n’est possible que si l’organisation fédérée est purement sur site et n’a jamais été fédérée avec un client hybride ou en ligne. Dans ce cas, la fédération avec ces organisations ne fonctionne pas tant qu’elles n’ont pas activé leur fournisseur d’hébergement.
>
> Si vous pensez que l’un de vos partenaires fédérés peut utiliser la fédération directe ou n’avoir été fédéré avec aucune organisation en ligne ou hybride, nous vous suggérons de leur envoyer une communication à ce sujet lorsque vous vous préparez à terminer votre migration vers le cloud.

## <a name="how-to-identify-stale-dns-records"></a>Comment identifier les enregistrements DNS obsolètes

Pour identifier les enregistrements DNS qui empêchent votre organisation de devenir tous les enregistrements Teams Uniquement, vous pouvez utiliser le Centre d’administration Teams pour modifier le mode de coexistence en TeamsOnly. Go to **Org-wide setting**  ->  **Teams Upgrade**. Tous les enregistrements DNS qui empêchent l’organisation de devenir Teams Uniquement seront inclus dans le message d’erreur.  Si aucun enregistrement DNS n’est trouvé, le mode de coexistence de votre organisation est changé en TeamsOnly. 

## <a name="how-to-remove-stale-dns-records"></a>Comment supprimer des enregistrements DNS obsolètes

Si votre organisation ne dispose plus d’utilisateurs locaux Skype Entreprise Server ou Lync Server, vous devez :

- Mettez à jour Skype Entreprise enregistrements DNS pour qu’ils pointent vers Microsoft 365 (au lieu du déploiement local).

- Supprimez Skype Entreprise enregistrements DNS si le domaine SIP n’est plus utilisé. 

Dans chaque domaine où se trouvent les enregistrements suivants, mettez-les à jour comme suit :

| Type d’enregistrement | Nom | Durée de vie | Priorité | Pondération | Port | Value (Valeur) |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  N/A |   N/A |   N/A |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    N/A |   N/A  | N/A |    sipdir.online.lync.com |
|||||||




