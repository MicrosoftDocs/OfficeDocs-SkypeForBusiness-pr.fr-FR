---
title: Configuration de la vue Galerie
TOCTitle: Configuration de la vue Galerie
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204871(v=OCS.15)
ms:contentKeyID: 49297119
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la vue Galerie

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans Lync Server 2013, vous configurez la fonctionnalité de visioconférence de la vue Galerie à l’aide de la stratégie de conférence. La vue Galerie est activée par défaut. Si vous ne souhaitez pas autoriser la vue Galerie ou si vous voulez l’autoriser pour certains utilisateurs seulement, vous devez désactiver la fonctionnalité dans la stratégie de conférence.

Quand la vidéo d’un participant à une conférence n’est pas disponible, l’expérience de la vue Galerie des utilisateurs peut être améliorée si vous déployez des photos haute résolution, une nouvelle fonctionnalité de Lync Server 2013. Les photos haute résolution permettent de remplacer les photos de contacts dont la résolution est plus faible et plus limitée, et qui sont stockées dans les services de domaine Active Directory. Les photos haute résolution sont stockées dans la boîte aux lettres Exchange 2013 de l’utilisateur correspondant. Ainsi, cela vous oblige à intégrer Lync Server 2013 à Exchange 2013. Pour plus d’informations, voir l’article du blog NextHop décrivant l’intégration d’Exchange 2013 et de Lync Server 2013 à l’adresse [http://go.microsoft.com/fwlink/?linkid=260987\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=260987%26clcid=0x40c).

> [!NOTE]  
> Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.

Vous pouvez afficher ou modifier les paramètres de la vue Galerie via le Panneau de configuration Lync Server 2013 ou à l’aide de l’une des applets de commande suivantes :

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configurez la vue Galerie à l’aide des paramètres de stratégie de conférence suivants :

  - **AllowMultiview**   Ce paramètre détermine si un utilisateur est autorisé à organiser des visioconférences dans la vue Galerie. Ce paramètre s’applique aux réunions planifiées et ad hoc créées par l’utilisateur.
    
    Exemples :
    
      - Ce paramètre a la valeur True pour l’utilisateur A, qui est hébergé dans un pool Lync Server 2013. Les réunions organisées par l’utilisateur A permettent aux utilisateurs d’envoyer et de recevoir plusieurs flux vidéo.
    
      - Ce paramètre a la valeur False pour l’utilisateur B, qui est hébergé dans un pool Lync Server 2013. Les réunions organisées par l’utilisateur B ont un seul flux vidéo, qui est similaire à l’expérience de visioconférence fournie par Lync Server 2010.
    
    Ce paramètre détermine quelles sont les personnes qui peuvent organiser des réunions autorisant plusieurs flux vidéo. Les participants aux réunions qui autorisent plusieurs flux vidéo peuvent être autorisés ou non à recevoir plusieurs flux vidéo, en fonction de leurs autorisations individuelles (voir la description du paramètre EnableMultiviewJoin).

  - **EnableMultiviewJoin**   Ce paramètre détermine si un participant à une réunion peut tirer parti de l’expérience vidéo de la vue Galerie dans les réunions où cette fonctionnalité est autorisée. Ce paramètre contrôle l’expérience de l’utilisateur dans les réunions auxquelles il participe.
    
    Exemples :
    
      - Ce paramètre a la valeur True pour l’utilisateur C. L’utilisateur C peut recevoir plusieurs flux vidéo quand il participe à une réunion organisée ou démarrée par l’utilisateur A. L’utilisateur C reçoit un flux vidéo unique similaire à l’expérience de visioconférence de Lync Server 2010, quand il participe à une réunion organisée ou démarrée par l’utilisateur B.
    
      - Ce paramètre a la valeur False pour l’utilisateur D. L’utilisateur D reçoit un flux vidéo unique similaire à l’expérience de visioconférence de Lync Server 2010, quand il participe à une réunion organisée par l’utilisateur B ou B.

La procédure suivante est un exemple d’utilisation de Lync Server Management Shell pour activer la visioconférence dans la vue Galerie.

## Pour modifier la stratégie de conférence de la visioconférence dans la vue Galerie

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true

