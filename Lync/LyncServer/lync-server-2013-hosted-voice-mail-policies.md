---
title: 'Lync Server 2013 : Stratégies de messagerie vocale hébergées'
TOCTitle: Stratégies de messagerie vocale hébergées
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398932(v=OCS.15)
ms:contentKeyID: 49298980
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Stratégies de messagerie vocale hébergées dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

Une *stratégie de messagerie vocale hébergée* fournit des informations à l’application de routage ExUM de Lync Server 2013 sur l’emplacement auquel les appels doivent être acheminés pour les utilisateurs dont les boîtes aux lettres se trouvent sur un service Exchange hébergé.

> [!NOTE]  
> Vous devez utiliser les stratégies de messagerie vocale hébergée pour intégrer Lync Server 2013 à la messagerie unifiée Exchange hébergée uniquement. Elles ne sont pas nécessaires dans le cas d’une intégration à la messagerie Exchange sur site.

## Étendue des stratégies de messagerie vocale hébergée

L’étendue des stratégies de messagerie vocale hébergée détermine le niveau hiérarchique d’application des stratégies. Vous pouvez configurer les stratégies de messagerie vocale hébergée avec les niveaux d’étendue suivants :

  - La stratégie *globale* peut potentiellement affecter tous les utilisateurs du déploiement Lync Server 2013. Si un utilisateur est activé pour l’accès à la messagerie unifiée Exchange hébergée, mais qu’aucune stratégie par utilisateur ne lui a été attribuée, et si aucune stratégie de site n’a été attribuée au site de l’utilisateur, la stratégie globale s’applique. La stratégie globale est installée avec Lync Server 2013. Vous pouvez la modifier en fonction de vos besoins, mais pas la renommer ni la supprimer.

  - Une stratégie de *site* peut concerner tous les utilisateurs hébergés sur le site pour lequel la stratégie est définie. Si aucune stratégie par utilisateur n’a été attribuée à un utilisateur configuré pour l’accès à la messagerie unifiée Exchange hébergée, la stratégie de site s’applique.

  - Une stratégie *par utilisateur* peut uniquement affecter des utilisateurs individuels ou des groupes. Pour appliquer une stratégie par utilisateur, vous devez l’attribuer explicitement à des utilisateurs individuels, des groupes et des objets contact.

> [!NOTE]  
> Généralement, une seule stratégie de messagerie vocale hébergée est requise. Dans de nombreux cas, vous pouvez modifier la stratégie globale pour qu’elle réponde à vos besoins. Si vous déployez plusieurs stratégies de messagerie vocale hébergée, toutes ont une étendue par utilisateur.

## Attributs des stratégies de messagerie vocale hébergée

Une stratégie de messagerie vocale définit deux attributs que l’application de routage de messagerie unifiée Exchange Lync Server 2013 insère dans la requête URI d’un message INVITE envoyé à l’implémentation de messagerie unifiée Exchange hébergée :

  - **Destination** : le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Cette valeur est utilisée par le serveur Edge Lync Server sur site à des fins de routage.
    
    > [!NOTE]  
    > Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.

  - **Organisation** : le nom de domaine complet du locataire sur le service de messagerie unifiée Exchange hébergé qui accueille les boîtes aux lettres de vos utilisateurs Lync Server 2013. Une stratégie de messagerie vocale peut contenir plusieurs organisations. Si plusieurs d’entre elles sont incluses dans la stratégie, cet attribut doit être une liste séparée par des virgules des locataires d’Exchange Server qui héberge les boîtes aux lettres de vos utilisateurs Lync Server 2013.

> [!NOTE]  
> L’administrateur client de votre service de messagerie unifiée Exchange hébergé fournit les valeurs nécessaires pour vos paramètres d’attribut de destination et d’organisation. Pour configurer votre stratégie, vous devez exécuter l’applet de commande New-CsHostedVoicemailPolicy ou utiliser Set-CsHostedVoicemailPolicy pour modifier une stratégie existante (la stratégie globale, par exemple).

Pour plus d’informations sur la gestion des stratégies de messagerie vocale hébergée, reportez-vous à la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

## Attribution de stratégies de messagerie vocale par utilisateur

Si votre stratégie de messagerie vocale hébergée est définie avec une étendue par utilisateur, vous devez l’attribuer explicitement. Vous pouvez exécute l’applet de commande Grant-CsHostedVoicemailPolicy pour attribuer la stratégie à des utilisateurs individuels ou des groupes.

Pour plus d’informations sur l’attribution ou la suppression d’une stratégie de messagerie vocale hébergée par utilisateur, reportez-vous aux applets de commande suivantes dans la documentation Lync Server Management Shell :

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

