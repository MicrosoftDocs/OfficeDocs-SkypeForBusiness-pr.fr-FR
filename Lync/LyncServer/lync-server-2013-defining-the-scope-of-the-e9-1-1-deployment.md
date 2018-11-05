---
title: 'Lync Server 2013 : Définition de l’étendue du déploiement E9-1-1'
TOCTitle: Définition de l’étendue du déploiement E9-1-1
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425775(v=OCS.15)
ms:contentKeyID: 49296725
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-06_

Avant de configurer Microsoft Lync Server 2013 pour E9-1-1, vous devez planifier son déploiement. Voici certaines des questions que vous pouvez vous poser :

  - **Quelles sont la stratégie et les obligations légales de votre organisation concernant E9-1-1 ?**  
    Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Renseignez-vous auprès de votre équipe juridique pour connaître les obligations s’appliquant à votre déploiement de Lync Server dans les zones géographiques souhaitées.

<!-- end list -->

  - **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**  
    Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.

<!-- end list -->

  - **Comment allez-vous déployer E9-1-1 sur des sites de succursale ?**  
    La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si les jonctions SIP d’E9-1-1 sont centralisées et si le réseau étendu subit une panne, les clients qui se connectent risquent de ne pas pouvoir obtenir un emplacement à partir du service d’informations sur l’emplacement ni de se connecter au fournisseur de services d’urgence. Lync Server fournit plusieurs stratégies permettant de gérer la résistance des communications vocales des sites de succursale, notamment : utilisation de réseaux de données résistants, déploiement d’une jonction SIP dans chaque succursale ou transfert des appels d’urgence vers la passerelle en cas de panne. Pour plus d’informations, reportez-vous à [Planification de la résistance vocale d’un site de succursale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**  
    L’acquisition d’emplacement automatique n’est disponible que pour les clients se trouvant sur le réseau de l’organisation, votre société doit donc décider si elle prendra en charge les appels E9-1-1 effectués à partir de clients Lync en dehors du site. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Cependant, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).
    
    > [!NOTE]  
    > Les clients Lync des utilisateurs qui se connectent au réseau de votre organisation à l’aide d’un VPN peuvent récupérer des informations d’adresses IP internes, mais comme elles ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN soient exclus du service d’informations sur l’emplacement.

<!-- end list -->

  - **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**  
    Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau RTC pour acheminer l’appel via une passerelle RTC locale.

