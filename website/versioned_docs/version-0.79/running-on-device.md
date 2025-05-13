**npx react-native init SkillZone
*import React from 'react';
import { View, Text, Button, StyleSheet, ScrollView } from 'react-native';

const App = () => {
  const [screen, setScreen] = React.useState('welcome'); // מצב מסך

  // פונקציות לכל מסך
  const showWelcomeScreen = () => setScreen('welcome');
  const showSportSelectionScreen = () => setScreen('sports');
  const showWorkoutScreen = () => setScreen('workout');

  // מסך פתיחה
  if (screen === 'welcome') {
    return (
      <View style={styles.container}>
        <Text style={styles.title}>ברוך הבא ל-SkillZone!</Text>
        <Button title="התחל לבחור ספורט" onPress={showSportSelectionScreen} />
      </View>
    );
  }

  // מסך בחירת ספורט
  if (screen === 'sports') {
    return (
      <View style={styles.container}>
        <Text style={styles.title}>בחר ספורט</Text>
        <Button title="כדורגל" onPress={showWorkoutScreen} />
        <Button title="כדורסל" onPress={showWorkoutScreen} />
        <Button title="טניס" onPress={showWorkoutScreen} />
        <Button title="שחייה" onPress={showWorkoutScreen} />
        <Button title="חזור" onPress={showWelcomeScreen} />
      </View>
    );
  }

  // מסך תוכנית אימון
  if (screen === 'workout') {
    return (
      <ScrollView style={styles.container}>
        <Text style={styles.title}>תוכנית אימון יומית</Text>
        <Text style={styles.subtitle}>כדורגל: אימון כושר ותרגול טכניקות בעיטה.</Text>
        <Button title="התחל אימון" onPress={() => alert('התחלת אימון!')} />
        <Button title="חזור לבחירת ספורט" onPress={showSportSelectionScreen} />
      </ScrollView>
    );
  }

  return null;
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 16,
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
  },
  subtitle: {
    fontSize: 18,
    marginBottom: 20,
  },
});

export default App;
****
