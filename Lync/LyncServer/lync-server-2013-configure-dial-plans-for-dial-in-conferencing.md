---
title: "Lync Server 2013 : Conf. des plans de numér. pour les conférences rendez-vous"
TOCTitle: Configuration des plans de numérotation pour les conférences rendez-vous
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412768(v=OCS.15)
ms:contentKeyID: 49298422
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-25_

Lorsque vous déployez la conférence rendez-vous, vous devez créer ou modifier un ou plusieurs plans de routage des numéros de téléphone d’accès entrant. Veillez à ce qu’au moins une règle de normalisation dans chaque plan convertisse les numéros de poste en numéros de téléphone complets au format E.164. Les utilisateurs de conférences rendez-vous participent à des conférences en tant qu’utilisateurs d’entreprise authentifiés en entrant leur code confidentiel et leur numéro de téléphone. Vous avez besoin d’une règle de normalisation pour convertir des postes en numéros de téléphone complets afin que les utilisateurs puissent être authentifiés lorsqu’ils saisissent simplement un numéro de poste.

Pour configurer des plans de numérotation pour la conférence rendez-vous, procédez comme suit :

  - Que vous déployiez ou non Voix Entreprise, modifiez le plan de numérotation global pour ajouter une région de conférence rendez-vous et veillez à ce qu’une règle de normalisation convertisse avec précision vos numéros d’accès. Pour obtenir des instructions détaillées, reportez-vous à [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Si vous n’avez pas déployé Voix Entreprise, créez des plans de numérotation pour vos numéros d’accès aux conférences rendez-vous. Veillez à inclure une région de conférence rendez-vous. Pour des instructions détaillées, reportez-vous à [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Si vous avez déployé Voix Entreprise, modifiez, si nécessaire, les plans de numérotation de Voix Entreprise pour inclure des régions et utilisez les règles de normalisation appropriées pour les numéros d’accès entrant. Pour des instructions détaillées, reportez-vous à [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Vous pouvez également créer des plans de numérotation dédiés, utilisés exclusivement pour les numéros d’accès entrant. Pour des instructions détaillées, reportez-vous à [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Pour plus d’informations sur la planification des régions, reportez-vous à [Configuration requise pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) dans la documentation de planification.

## Dans cette section

  - [Affichage des informations d’un plan de numérotation dans Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

