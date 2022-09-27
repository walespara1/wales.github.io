import React, { Component } from 'react';
import { Dimensions } from 'react-native';
import { StyleProvider } from '@shoutem/theme';
import {
  Card,
  Image,
  View,
  Subtitle,
  Caption,
} from '@shoutem/ui';

const window = Dimensions.get('window');

const Colors = {
  BACKGROUND: '#ffffff',
  SHADOW: '#000000',
};

const MEDIUM_GUTTER = 15;

const theme = {
  'shoutem.ui.View': {
    '.h-center': {
      alignItems: 'center',
    },

    '.v-center': {
      justifyContent: 'center',
    },

    '.flexible': {
      flex: 1,
    },

    flexDirection: 'column',
  },

  'shoutem.ui.Card': {
    'shoutem.ui.View.content': {
      'shoutem.ui.Subtitle': {
        marginBottom: MEDIUM_GUTTER,
      },

      flex: 1,
      alignSelf: 'stretch',
      padding: 10,
    },

    width: (180 / 375) * window.width,
    flexDirection: 'column',
    justifyContent: 'center',
    alignItems: 'flex-start',
    backgroundColor: Colors.BACKGROUND,
    borderRadius: 2,
    shadowColor: Colors.SHADOW,
    shadowOpacity: 0.1,
    shadowOffset: { width: 1, height: 1 },
  },

  'shoutem.ui.Image': {
    '.medium-wide': {
      width: (180 / 375) * window.width,
      height: 85,
    },

    flexDirection: 'column',
    alignItems: 'center',
    justifyContent: 'center',
    backgroundColor: Colors.BACKGROUND,
  },
};

export default class App extends Component<{}> {
  render() {
    return (
      <StyleProvider style={theme}>
        <View styleName="flexible vertical v-center h-center">
          <Card>
            <Image
              styleName="medium-wide"
              source={{ uri: 'http://shoutem.github.io/img/ui-toolkit/examples/image-12.png' }}
            />
            <View styleName="content">
              <Subtitle numberOfLines={4}>
                Lady Gaga Sings National Anthem at Super Bowl 50
              </Subtitle>
              <Caption>21 hours ago</Caption>
            </View>
          </Card>
        </View>
      </StyleProvider>
    );
  }
}
