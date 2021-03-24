---
title: 'Programme de fin de vie pour l’intégration de Skype Entreprise à des fournisseurs de services d’audioconférence tiers '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Le 31 juillet 2021, le programme de fin de vie se terminera par l’intégration de Skype Entreprise à des fournisseurs de services d’audioconférence tiers.
ms.openlocfilehash: 5e48c7deb114136e0b12c2636cf562213890656d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100770"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Programme de fin de vie pour l’intégration de Skype Entreprise à des fournisseurs de services d’audioconférence tiers 

Microsoft a annoncé le début du programme de fin de vie pour l’intégration de Skype Entreprise à des fournisseurs de services d’audioconférence tiers. 

Le programme de fin de vie se terminera le 31 juillet 2021. Au terme du programme, l’intégration de Skype Entreprise à des fournisseurs de services d’audioconférence tiers cessera de fonctionner et les modifications suivantes seront observées à cette date (31 juillet 2021) :

- Les participants qui tentent de participer à une réunion Skype Entreprise par le biais de numéros de connexion fournis par un service d’acp tiers ne seront plus connectés à la réunion Skype Entreprise.
 
- Les informations de connexion des utilisateurs activés pour un service d’acp tiers ne seront plus incluses automatiquement dans les nouvelles invitations aux réunions Skype Entreprise.

Dans le cadre de l’annonce du début du programme de fin de vie, le changement suivant est pris en compte et restera en place jusqu’au terme du programme de fin de vie : 

- Les clients sans utilisateur Skype Entreprise configuré pour utiliser un service ACP tiers ne pourront pas configurer les utilisateurs de manière à utiliser un service d’ACP tiers.

- Les clients existants avec des utilisateurs Skype Entreprise configurés pour utiliser un service ACP tiers pourront toujours ajouter de nouveaux utilisateurs pendant la durée de la période de fin de vie. Veuillez noter que nous ne recommandons pas de mettre en place des utilisateurs Skype Entreprise supplémentaires de telles personnes, car les modifications qui entreront en vigueur le 31 juillet 2021 s’appliqueront également à ces utilisateurs.

## <a name="preparing-for-this-change"></a>Préparation de cette modification

Pour préparer ce changement, nous encourageons les organisations concernées à informer leurs utilisateurs activés de cette mise à jour planifiée avant le 31 juillet 2021. 

Depuis le 31 juillet 2021, les utilisateurs peuvent continuer à utiliser Skype Entreprise sans interruption de leurs réunions en ligne. Toutefois, les organisations devront activer l’audioconférence fournie par Microsoft pour leurs utilisateurs qui ont besoin d’une audioconférence avec Skype Entreprise ou Microsoft Teams. Pour en savoir plus sur l’audioconférence Microsoft, consultez [audioconférence.](https://products.office.com/skype-for-business/audio-conferencing) 

En fonction de l’état final souhaité d’une organisation, trois chemins peuvent être suivis :

- Migrer vers l’audioconférence Microsoft. 
- Continuez à utiliser séparément un fournisseur de services d’audioconférence tiers. 
- Arrêtez complètement d’utiliser les conférences téléphoniques.

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>Chemin d#1 : migrer vers Microsoft Audioconférence   

Les organisations qui décident de migrer vers l’audioconférence Microsoft et de terminer leur migration avant le 31 juillet 2021 n’auront aucun impact sur le service pendant ou après cette date. La migration vers l’audioconférence Microsoft introduira les modifications suivantes pour une organisation : 

- Ce service sera facturé avec tous les autres services Microsoft 365 ou Office 365. 

- Si l’abonnement standard est acheté, le coût d’appel payant sera inclus dans le coût mensuel de l’abonnement par utilisateur. 

- Un nouvel ensemble de numéros de téléphone à composer sera fourni à chaque organisation et à ses utilisateurs. Pour obtenir une couverture géographique du service d’audioconférence Microsoft, consultez la disponibilité des pays et régions pour les plans [d’audioconférence et d’appel.](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
 
- Les réunions déjà programmées par des utilisateurs activés avec un ACP tiers seront automatiquement reprogrammées de manière à inclure les informations de connexion à l’audioconférence Microsoft.
 
- Les ID de conférence de chaque réunion sont dynamiques, ce qui signifie que chaque réunion a son propre ID de conférence dédié. Les ID de conférence dynamiques offrent une sécurité accrue et une expérience améliorée pour les réunions dos-à-dos.

- Toute utilisation du service est soumise aux conditions d’utilisation des services d’audioconférence. 

La migration vers Microsoft AudioConférence est simple et peut être effectuée en quelques étapes seulement après l’acquisition des licences pour le service. Pour en savoir plus sur la migration vers Microsoft AudioConférence, voir :

- [Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**Résumé :**

- Les organisations qui migrent vers Microsoft AudioConférence et qui terminent leur migration avant le 31 juillet 2021 n’auront aucun impact sur leur service pendant ou après cette date.

- Pour en savoir plus sur la migration vers Microsoft AudioConférence, voir Essayer ou acheter l’audioconférence dans [Microsoft 365 ou Office 365.](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>Chemin d#2 : continuer à utiliser un fournisseur de services d’audioconférence tiers séparément

Les organisations qui décident de continuer d’utiliser un fournisseur de services d’audio acp tiers comme après le 31 juillet 2021 auront un impact sur le service, car les informations de rendez-vous d’ACP tierces ne pourront plus être utilisées pour rejoindre la partie audio d’une réunion Skype Entreprise. 

Pour éviter la fragmentation de l’audio dans les réunions Skype Entreprise en faisant en sorte que certains participants la rejoignent via VoIP et d’autres via le système d’audiocondiffrable tiers, il est recommandé pour ces organisations de désactiver l’utilisation de VoIP dans les réunions de leurs utilisateurs. Ainsi, tous les participants devront rejoindre la partie audio d’une réunion à l’aide du acp tiers et toutes les autres charges de travail de la réunion (telles que la conversation ou le partage d’écran) peuvent continuer à être pris en charge sur Skype Entreprise. 

- Pour désactiver VoIP pour toutes les réunions d’un organisateur donné, définissez le paramètre AllowIPAudio de sa stratégie de conférence sur false via l'Set-CsConferencingPolicy de réunion. Pour plus d’informations, [voir Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
En termes de planification et à compter du 31 juillet 2021, les informations de connexion d’un ACP tiers ne seront plus incluses automatiquement dans les invitations aux réunions Skype Entreprise. Les utilisateurs doivent ajouter manuellement les informations d’accès dans leurs invitations aux réunions Skype Entreprise s’ils souhaitent continuer à inclure ces informations dans leurs réunions. 

Veuillez noter que le 31 juillet 2021, les réunions existantes des utilisateurs ne seront pas reprogrammées automatiquement de manière à supprimer les informations de connexion tierces d’ACP. Les organisations qui décident de conserver le voIP activé pour les réunions de leurs utilisateurs doivent envisager de désactiver l’intégration d’ACP tiers pour leurs utilisateurs et de reprogrammer leurs réunions à l’aide du service de migration des réunions pour supprimer les informations de rendez-vous d’audioconférence tierces de leurs réunions existantes et éviter la fragmentation de l’audio sur les réunions déjà programmées. 

- Pour désactiver l’intégration de l’audioconférence tierce pour un organisateur donné, utilisez l'Remove-CsUserAcp dlet. Pour plus d’informations, [voir Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Pour reprogrammer automatiquement les réunions des utilisateurs après la désactivation de l’intégration à un fournisseur de services d’audioconférence tiers, consultez « Comment puis-je exécuter manuellement la migration de réunion pour un utilisateur ? dans [Configuration de Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md) 

**Résumé :**

- Les organisations qui décident de continuer d’utiliser un ACP tiers après le 31 juillet 2021 seront concernées, car un ACP tiers ne pourra pas être utilisé pour participer à une réunion Skype Entreprise et les nouvelles réunions n’incluront pas les informations de rendez-vous d’ACP tierces. 

- Avant le 31 juillet 2021, il est recommandé de désactiver le VoIP pour toutes les réunions des utilisateurs concernés afin d’éviter que l’audio soit fragmenté parmi les participants rejoignant la réunion via VoIP et via un ACP tiers. 

    - Pour désactiver VoIP de toutes les réunions d’un organisateur donné, définissez le paramètre AllowIPAudio de la stratégie de conférence de l’utilisateur sur False via l'Set-CsConferencingPolicy de détail. Pour plus d’informations, [voir Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
- Si une organisation ne désactive pas VoIP pour toutes les réunions, il est recommandé de désactiver l’intégration de Skype Entreprise Online à un ACP tiers et de reprogrammer leurs réunions afin de supprimer les informations de connexion d’ACP tierces afin d’éviter la fragmentation de l’audio.

    - Pour désactiver l’intégration de l’audioconférence tierce pour un organisateur donné, utilisez l’cmdlet [Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

    - Pour reprogrammer automatiquement les réunions, voir « Comment puis-je exécuter manuellement la migration de réunion pour un utilisateur ? dans [Configuration de Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>Chemin d#3 : cesser entièrement d’utiliser les conférences téléphoniques

Les organisations qui décident d’arrêter complètement l’utilisation des conférences rendez-vous (ni fournies par Microsoft ni par un ACP tiers) peuvent entièrement compter sur VoIP pour prendre en charge la partie audio d’une réunion Skype Entreprise. 

Ces organisations doivent désactiver l’utilisation d’un fournisseur de services d’audioconférence tiers et reprogrammer leurs réunions automatiquement à l’aide du service de migration des réunions pour supprimer leurs informations de conférence rendez-vous. 

- Pour désactiver l’intégration de l’audioconférence tierce pour un organisateur donné, utilisez l'Remove-CsUserAcp dlet. Pour plus d’informations, [voir Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Pour reprogrammer automatiquement les réunions des utilisateurs après la désactivation de l’intégration à un fournisseur de services d’audioconférence tiers, consultez « Comment puis-je exécuter manuellement la migration de réunion pour un utilisateur ? dans [Configuration de Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md) 

**Résumé :** 

- Les organisations qui décident d’arrêter l’audioconférence avant le 31 juillet 2021 ne seront pas impactées.

- Pour désactiver l’intégration de l’audioconférence tierce pour un organisateur donné, utilisez l'Remove-CsUserAcp dlet. Pour plus d’informations, [voir Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Pour reprogrammer automatiquement les réunions des utilisateurs après la désactivation de l’intégration à des fournisseurs de services d’audioconférence tiers, consultez « Comment puis-je exécuter manuellement la migration de réunion pour un utilisateur ? dans [Configuration de Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)