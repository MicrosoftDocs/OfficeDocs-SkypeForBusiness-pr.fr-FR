---
title: "Lync Server 2013 : Dév. du trafic mult. et contrôle d’admission des appels"
TOCTitle: Déviation du trafic multimédia et contrôle d’admission des appels
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398203(v=OCS.15)
ms:contentKeyID: 49296309
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

La déviation du trafic multimédia et le contrôle d’admission des appels fonctionnent conjointement pour gérer le contrôle de la bande passante pour le trafic des données multimédias pendant les appels. La déviation du trafic multimédia facilite le flux des données multimédias sur des liaisons correctement connectées ; le contrôle d’admission des appels, quant à lui, gère le trafic sur les liaisons avec des restrictions de bande passante. Étant donné que la déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement, vous devez tenir compte de l’un lorsque vous planifiez l’utilisation de l’autre. Les combinaisons suivantes sont prises en charge :

  - La déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés. La déviation du trafic multimédia doit être définie sur **Utiliser les informations de site et de région** . Ces informations sont les mêmes que celles utilisées pour le contrôle d’admission des appels.
    
    Si vous activez le contrôle d’admission des appels, vous ne pouvez pas sélectionner **Toujours ignorer** et inversement, car les deux configurations s’excluent mutuellement. C’est-à-dire, qu’une seule configuration s’appliquera à un appel RTC donné. D’abord, une vérification a lieu pour déterminer si la déviation du trafic multimédia s’applique à l’appel. Si c’est le cas, le contrôle d’admission des appels n’est pas utilisé. Cela est logique, car si la déviation du trafic multimédia peut être appliqué à l’appel, celui-ci utilise par définition une connexion où le contrôle d’admission des appels n’est pas nécessaire. En revanche, si le contournement ne peut pas être appliqué à l’appel (c’est-à-dire, si les ID de contournement du client et de la passerelle ne correspondent pas), alors le contrôle d’admission des appels est appliqué à l’appel.

  - Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Toujours ignorer** .
    
    Dans cette configuration, les sous-réseaux du client et de la jonction sont mappés à un seul ID de contournement, qui est calculé par le système.

  - Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Utiliser les informations de site et de région** .
    
    Lorsque **Utiliser les informations de site et de région** est activé, la vérification pour déterminer si le contournement doit s’appliquer fonctionne essentiellement de la même manière, que le contrôle d’admission des appels soit activé ou non. C’est-à-dire que, pour un appel RTC donné, le sous-réseau du client est mappé à un site particulier, et l’ID de contournement pour ce sous-réseau est extrait. De même, le sous-réseau de la passerelle est mappé à un site particulier et l’ID de contournement pour ce sous-réseau est extrait. Le contournement aura lieu pour l’appel uniquement si les deux ID de contournement sont identiques. Si ce n’est pas le cas, la déviation du trafic multimédia n’aura pas lieu.
    
    Même si le contrôle d’admission des appels est désactivé globalement, la stratégie de bande passante doit être définie pour chaque site et liaison si vous voulez utiliser la configuration site-et-région pour décider d’appliquer le contournement ou non. La valeur réelle de la restriction de la bande passante ou le mode de celle-ci n’a aucune importance. L’objectif est que le système calcule automatiquement différents ID de contournement à associer à différents emplacements qui ne sont pas correctement connectés. Définir une restriction de bande passante signifie par définition qu’une liaison n’est pas correctement connectée.

  - Le contrôle d’admission des appels est activé et la déviation du trafic multimédia n’est pas activée. Cela s’applique uniquement lorsque toutes les passerelles et les PBX IP ne sont pas correctement connectés ou ne remplissent pas toutes les conditions pour la déviation du trafic multimédia. Pour plus d’informations sur les conditions requises pour la déviation du trafic multimédia, reportez-vous à [Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

## Voir aussi

#### Concepts

[Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

